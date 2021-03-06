<template>
  <vl-page>
    <vl-region mod-no-space-bottom>
      <vl-layout>
        <header class="wp-pt-heading">
          <div class="wp-pt-heading__parent">
            <vl-link to="/" mod-bold>Overzicht</vl-link>
          </div>

          <div class="wp-pt-heading__title-wrapper">
            <vl-title tag-name="h1" class="wp-pt-heading__title">Basisregisters Vlaanderen</vl-title>
          </div>

          <vl-grid>
            <vl-column width="9" width-s="12">
              <div class="wp-pt-heading__content">
                <vl-typography>
                  <vl-introduction>
                    Bent u op zoek naar authentieke gegevensbronnen? Dan bent u bij
                    <strong>Informatie Vlaanderen</strong> aan het juiste adres.
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
            <vl-column width="8" width-m="9" width-s="12">
              <vl-grid mod-stacked>
                <vl-column width="12">
                  <vl-title id="algemeen" tag-name="h2">Wat zijn de basisregisters?</vl-title>

                  <vl-typography>
                    <p>
                      Ter verbetering van haar beleidsvoering en dienstverlening trekt de Vlaamse overheid
                      volop de kaart van de uitbouw van een geïntegreerd stelsel van authentieke gegevensbronnen.
                    </p>
                    <p><vl-link to="/algemeen" icon="arrow-right-fat" mod-block mod-icon-before>Lees verder</vl-link></p>
                  </vl-typography>
                </vl-column>

                <vl-column width="12">
                  <vl-title id="aanleiding" tag-name="h2">Aanleiding voor de basisregisters</vl-title>

                  <vl-typography>
                    <p>
                      Informatie is zeer omvangrijk, maar ook zeer versnipperd.
                      De basisregisters moeten zorgen voor een efficiëntere doorstroming van informatie naar alle betrokken partijen.
                    </p>
                    <p><vl-link to="/aanleiding" icon="arrow-right-fat" mod-block mod-icon-before>Lees verder</vl-link></p>
                  </vl-typography>
                </vl-column>

                <vl-column width="12">
                  <vl-title id="visie" tag-name="h2">Visie op de basisregisters</vl-title>

                  <vl-typography>
                    <p>
                      De basisregisters worden ontwikkeld in samenspraak met de belangrijkste stakeholders. 
                      De ontwikkeling van de registers bespreken we in werkgroepen. Daarbij houden we maximaal rekening met de relevante doelgroepen.
                    </p>
                    <p><vl-link to="/visie" icon="arrow-right-fat" mod-block mod-icon-before>Lees verder</vl-link></p>
                  </vl-typography>
                </vl-column>

                <vl-column width="12">
                  <vl-title id="aanbod" tag-name="h2">Aanbod van gegevensbronnen</vl-title>

                  <vl-typography class="vl-u-spacer--medium">
                    <p>Volgende gegevensbronnen maken momenteel deel uit van het stelsel:</p>
                  </vl-typography>

                  <vl-grid mod-stacked>
                    <vl-column width="4" width-m="6" width-s="12">
                      <vl-link-list>
                        <vl-link-list-item>
                          <vl-spotlight
                            title="Gemeenten"
                            subtitle="Referentie bron"
                            text="de Belgische gemeenten"
                            tag-name="router-link"
                            to="registers/gemeenten">
                          </vl-spotlight>
                        </vl-link-list-item>
                      </vl-link-list>
                    </vl-column>

                    <vl-column width="4" width-m="6" width-s="12">
                      <vl-link-list>
                        <vl-link-list-item>
                          <vl-spotlight
                            title="Postinfo"
                            subtitle="Referentie bron"
                            text="de Belgische postcodes"
                            tag-name="router-link"
                            to="registers/postinfo">
                          </vl-spotlight>
                        </vl-link-list-item>
                      </vl-link-list>
                    </vl-column>

                    <vl-column width="4" width-m="6" width-s="12">
                      <vl-link-list>
                        <vl-link-list-item>
                          <vl-spotlight
                            title="Straatnamen"
                            subtitle="Authentieke bron"
                            text="de Vlaamse straatnamen"
                            tag-name="router-link"
                            to="registers/straatnamen">
                          </vl-spotlight>
                        </vl-link-list-item>
                      </vl-link-list>
                    </vl-column>

                    <vl-column width="4" width-m="6" width-s="12">
                      <vl-link-list>
                        <vl-link-list-item>
                          <vl-spotlight
                            title="Adressen"
                            subtitle="Authentieke bron"
                            text="de Vlaamse adressen"
                            tag-name="router-link"
                            to="registers/adressen">
                          </vl-spotlight>
                        </vl-link-list-item>
                      </vl-link-list>
                    </vl-column>

                    <vl-column width="4" width-m="6" width-s="12">
                      <vl-link-list>
                        <vl-link-list-item>
                          <vl-spotlight
                            title="Gebouwen"
                            subtitle="Authentieke bron"
                            text="de Vlaamse gebouwen en gebouweenheden"
                            tag-name="router-link"
                            to="registers/gebouwen">
                          </vl-spotlight>
                        </vl-link-list-item>
                      </vl-link-list>
                    </vl-column>

                    <vl-column width="4" width-m="6" width-s="12">
                      <vl-link-list>
                        <vl-link-list-item>
                          <vl-spotlight
                            title="Percelen"
                            subtitle="Referentie bron"
                            text="de Vlaamse percelen"
                            tag-name="router-link"
                            to="registers/percelen">
                          </vl-spotlight>
                        </vl-link-list-item>
                      </vl-link-list>
                    </vl-column>

                    <vl-column width="4" width-m="6" width-s="12">
                      <vl-link-list>
                        <vl-link-list-item>
                          <vl-spotlight
                            title="Wegen"
                            subtitle="Authentieke bron"
                            text="de Vlaamse wegen"
                            tag-name="router-link"
                            to="registers/wegen">
                          </vl-spotlight>
                        </vl-link-list-item>
                      </vl-link-list>
                    </vl-column>

                    <vl-column width="4" width-m="6" width-s="12">
                      <vl-link-list>
                        <vl-link-list-item>
                          <vl-spotlight
                            title="Organisaties"
                            subtitle="Authentieke bron"
                            text="de Vlaamse organisaties en organen"
                            tag-name="router-link"
                            to="registers/organisaties">
                          </vl-spotlight>
                        </vl-link-list-item>
                      </vl-link-list>
                    </vl-column>

                    <vl-column width="4" width-m="6" width-s="12">
                      <vl-link-list>
                        <vl-link-list-item>
                          <vl-spotlight
                            title="Dienstverleningen"
                            subtitle="Authentieke bron"
                            text="de Vlaamse dienstverlening"
                            tag-name="router-link"
                            to="registers/dienstverleningen">
                          </vl-spotlight>
                        </vl-link-list-item>
                      </vl-link-list>
                    </vl-column>
                  </vl-grid>
                </vl-column>
              </vl-grid>
            </vl-column>

            <vl-column
              width="3"
              push="1"
              push-m="reset"
              width-s="12"
              class="wp-pt-side-navigation wp-pt-side-navigation--sticky-parent">
              <aside class="wp-pt-side-navigation--sticky" style="top: 120px;">
                <vl-side-navigation title="Op deze pagina">
                  <vl-side-navigation-list>
                    <vl-side-navigation-item href="#algemeen" text="Algemeen" />
                    <vl-side-navigation-item href="#aanleiding" text="Aanleiding" />
                    <vl-side-navigation-item href="#visie" text="Visie" />
                    <vl-side-navigation-item href="#aanbod" text="Aanbod" />
                  </vl-side-navigation-list>
                </vl-side-navigation>
              </aside>
            </vl-column>
          </vl-grid>
        </vl-layout>
      </vl-region>
    </vl-main>
  </vl-page>
</template>
