<template>
  <status-category
    title="Cache"
    :category-id="categoryId"
    :alert-level="alertLevel"
    :show-refresh="!isLoading"
    @refreshCategory="refresh">

    <vl-column v-if="noData" width="12">
      <div v-if="isLoading" v-vl-align:center>
        <vl-loader message="De status van de cache wordt opgevraagd." />
      </div>
      <vl-alert
        v-else
        title="Cache status ophalen is mislukt"
        content="Er is iets fout gelopen tijdens het ophalen van de status van de cache. Probeer het later opnieuw."
        mod-error />
    </vl-column>

    <status-item
      v-for="cache in caches"
      :key="cache.name"
      :item-id="createItemId(cache.name)"
      :alert-level="cache.alertLevel"
      class="cache">
      <div class="name state">{{ cache.name }}</div>
      <div v-if="cache.numberOfRecordsToProcess > 0" class="--right">Aantal niet gecachte objecten: {{ cache.numberOfRecordsToProcess }}</div>
    </status-item>

  </status-category>
</template>

<style lang="scss">
</style>

<script>
import StatusCategory from './StatusCategory.vue';
import StatusItem from './StatusItem.vue';
import { createCacheStatusModel, aggregateAlertLevel } from './transform.js';

export default {
  name: 'CacheStatus',
  components: {
    StatusCategory,
    StatusItem,
  },
  props: {
    registeryId: {
      type: String,
      required: true,
    },
    status: {
      type: Array,
      required: false,
      default: null,
    },
    isLoading: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
  computed: {
    categoryId: function() {
      return `${this.registeryId}_cache`.toLocaleLowerCase();
    },
    noData: function() {
      return !this.status || this.status.length == 0;
    },
    alertLevel: function() {
      return this.noData ? 'none' : aggregateAlertLevel(this.caches);
    },
    caches : function () {
      return (this.status || []).map(createCacheStatusModel);
    },
  },
  methods: {
    refresh: function () {
      this.$emit('refresh');
    },
    createItemId: function(itemId) {
      return `${this.categoryId}_${itemId}`
        .replace(/\./g, '-')
        .toLocaleLowerCase();
    },
  },
};
</script>
