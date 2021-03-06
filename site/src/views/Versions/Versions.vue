<template>
  <vl-page>
    <vl-region mod-no-space-bottom>
      <vl-layout>
        <header class="wp-pt-heading">
          <div class="wp-pt-heading__parent">
            <vl-link to="/" mod-bold>Overzicht</vl-link>
          </div>

          <div class="wp-pt-heading__title-wrapper">
            <vl-title tag-name="h1" class="wp-pt-heading__title">Versies</vl-title>
          </div>

          <vl-grid>
            <vl-column width="9" width-s="12">
              <div class="wp-pt-heading__content">
                <vl-typography>
                  <vl-introduction>
                    Wat draait er <strong>momenteel</strong> allemaal? Bekijk hier het live overzicht!
                  </vl-introduction>
                </vl-typography>
              </div>
            </vl-column>
          </vl-grid>
        </header>
      </vl-layout>
    </vl-region>

    <vl-main>
      <vl-region>
        <vl-layout>
          <vl-grid mod-stacked>
            <vl-column width="12">
              <vl-grid mod-stacked>
                <vl-column v-if="!loaded && !error" width="12">
                  <div v-vl-align:center>
                    <vl-loader message="De versies worden opgevraagd" />
                  </div>
                </vl-column>

                <vl-column v-if="error" width="12">
                  <vl-alert
                    title="Versies ophalen mislukt"
                    content="Er is iets fout gelopen tijdens het ophalen van de versies. Probeer later opnieuw."
                    mod-error />
                </vl-column>

                <vl-column v-if="loaded" width="4" width-m="6" width-s="12">
                  <version
                    title="Gemeenten"
                    text="de Belgische gemeenten."
                    to="/registers/gemeenten"
                    :version="versions.municipalityRegistry" />
                </vl-column>

                <vl-column v-if="loaded" width="4" width-m="6" width-s="12">
                  <version
                    title="Postinfo"
                    text="de Belgische postcodes."
                    to="/registers/postinfo"
                    :version="versions.postalRegistry" />
                </vl-column>

                <vl-column v-if="loaded" width="4" width-m="6" width-s="12">
                  <version
                    title="Straatnamen"
                    text="de Vlaamse straatnamen."
                    to="/registers/straatnamen"
                    :version="versions.streetNameRegistry" />
                </vl-column>

                <vl-column v-if="loaded" width="4" width-m="6" width-s="12">
                  <version
                    title="Adressen"
                    text="de Vlaamse adressen."
                    to="/registers/adressen"
                    :version="versions.addressRegistry" />
                </vl-column>

                <vl-column v-if="loaded" width="4" width-m="6" width-s="12">
                  <version
                    title="Gebouwen"
                    text="de Vlaamse gebouwen en gebouweenheden."
                    to="/registers/gebouwen"
                    :version="versions.buildingRegistry" />
                </vl-column>

                <vl-column v-if="loaded" width="4" width-m="6" width-s="12">
                  <version
                    title="Percelen"
                    text="de Vlaamse percelen."
                    to="/registers/percelen"
                    :version="versions.parcelRegistry" />
                </vl-column>

                <vl-column v-if="loaded" width="4" width-m="6" width-s="12">
                  <version
                    title="Wegen"
                    text="de Vlaamse wegen."
                    to="/registers/wegen"
                    version="N/A" />
                </vl-column>

                <vl-column v-if="loaded" width="4" width-m="6" width-s="12">
                  <version
                    title="Organisaties"
                    text="de Vlaamse organisaties en organen."
                    to="/registers/organisaties"
                    :version="versions.organisationRegistry" />
                </vl-column>

                <vl-column v-if="loaded" width="4" width-m="6" width-s="12">
                  <version
                    title="Dienstverleningen"
                    text="de Vlaamse dienstverlening."
                    to="/registers/dienstverleningen"
                    :version="versions.publicServiceRegistry" />
                </vl-column>
                
                <vl-column v-if="loaded" width="4" width-m="6" width-s="12">
                  <version
                    title="Api"
                    text="de Basisregisters Vlaanderen API."
                    to="/registers/api"
                    :version="versions.publicApi" />
                </vl-column>
                
                <vl-column v-if="loaded" width="4" width-m="6" width-s="12">
                  <version
                    title="Website"
                    text="de Basisregisters Vlaanderen website."
                    to="/registers/site"
                    :version="versions.publicSite" />
                </vl-column>
              </vl-grid>
            </vl-column>
          </vl-grid>
        </vl-layout>
      </vl-region>
    </vl-main>
  </vl-page>
</template>

<script>
import Version from './Version.vue';
import axios from 'axios';

export default {
  name: 'Versions',
  components: {
    Version,
  },
  data () {
    return {
      loaded: false,
      error: false,
      versions: {
        addressRegistry: '?',
        buildingRegistry: '?',
        municipalityRegistry: '?',
        parcelRegistry: '?',
        postalRegistry: '?',
        publicApi: '?',
        publicServiceRegistry: '?',
        streetNameRegistry: '?',
      },
    };
  },
  mounted () {
    axios
      .get(window.baseRegistriesApi + '/v1/versions')
      .then(({ data: { components = {} } }) => {
        this.versions = components;
        this.loaded = true;
      })
      .catch(error => {
        this.error = true;
        console.log('Could not get versions.', error);
      });
  },
};
</script>
