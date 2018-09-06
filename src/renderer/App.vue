<template>
  <div id="app">
    <v-app dark>
      <!-- <v-navigation-drawer
        fixed
        :mini-variant="true"
        :clipped="clipped"
        v-model="drawer"
        app
      >
        <v-list>
          <v-list-tile 
            router
            :to="item.to"
            :key="i"
            v-for="(item, i) in items"
            exact
          >
            <v-list-tile-action>
              <v-icon v-html="item.icon"></v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-content v-text="item.title"></v-list-tile-content>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer> -->
      <v-toolbar fixed app :clipped-left="clipped">
        <v-menu offset-y>
            <v-btn slot="activator" depressed>
                <span>
                    <v-icon>storage</v-icon>  MASTER DATA
                </span>
            </v-btn>
            <v-list>
                <v-menu offset-x open-on-hover>
                    <v-list-tile @click="" slot="activator">
                        <v-list-tile-content>Malha Ferroviária</v-list-tile-content>
                        <v-list-tile-action>
                            <v-btn icon ripple>
                                <v-icon color="grey lighten-1">chevron_right</v-icon>
                            </v-btn>
                        </v-list-tile-action>
                    </v-list-tile>
                    <v-list dense>
                        <v-list-tile @click="">
                            <v-list-tile-content>Seções de Bloqueio</v-list-tile-content>
                        </v-list-tile>
                        <v-list-tile @click="">
                            <v-list-tile-content>Locais Ferroviários</v-list-tile-content>
                        </v-list-tile>
                        <v-list-tile @click="">
                            <v-list-tile-content>Classificações de Seções de Bloqueio</v-list-tile-content>
                        </v-list-tile>
                    </v-list>
                </v-menu>

                <v-list-tile>
                    <v-list-tile-content>Trem</v-list-tile-content>
                </v-list-tile>
                <v-list-tile>
                    <v-list-tile-content>Classe Trem</v-list-tile-content>
                </v-list-tile>
                <v-list-tile>
                    <v-list-tile-content>Trem Tipo</v-list-tile-content>
                </v-list-tile>
                <v-list-tile>
                    <v-list-tile-content>Condições Operacionais</v-list-tile-content>
                </v-list-tile>
            </v-list>
        </v-menu>

        <v-btn depressed>
            <span>
                <v-icon>show_chart</v-icon>  GRÁFICO DE TRENS
            </span>
        </v-btn>

        <v-menu offset-y>
            <v-btn slot="activator" depressed>
                <span>
                    <v-icon>settings</v-icon>  CONFIGURAÇÔES
                </span>
            </v-btn>
            <v-list>
                <v-list-tile>
                    <v-list-tile-content>Parâmetros do Sistema</v-list-tile-content>
                </v-list-tile>
                <v-list-tile>    
                    <v-list-tile-content>Parâmetros de Otimização</v-list-tile-content>
                </v-list-tile>
                <v-list-tile>
                    <v-list-tile-content>Configurações de Temas</v-list-tile-content>
                </v-list-tile>
            </v-list>
        </v-menu>

        <v-spacer></v-spacer>

        <v-menu offset-y :close-on-content-click="false">
            <v-btn icon slot="activator">
                <v-icon>person</v-icon>
            </v-btn>
            <v-layout row wrap style="background: black; padding: 20px;">
                <v-layout column align-center>
                    <v-avatar color="indigo" size="128"> 
                        <v-icon>account_circle</v-icon>
                    </v-avatar>
                    <span style="font-size: 16px;">c0121160</span>
                    <span style="">Administrator</span>

                    <v-divider></v-divider>

                    <div>
                        <v-select 
                            label="Ferrovia"
                            v-model="ferrovia"
                            :items="['EFC', 'EFVM']"
                        ></v-select>
                        <v-select 
                            label="Idioma"
                            v-model="lingua"
                            :items="['Portugues', 'Ingles']"
                        ></v-select>
                        <v-select 
                            label="Tema"
                            v-model="tema"
                            :items="['Claro', 'Escuro']"
                        ></v-select>
                    </div>
                </v-layout>
            </v-layout>
        </v-menu>



      </v-toolbar>
      <v-content>
        <v-container fluid fill-height>
          <v-slide-y-transition mode="out-in">
            <router-view></router-view>
          </v-slide-y-transition>
        </v-container>
      </v-content>
      <v-footer :fixed="fixed" app>
        <v-spacer></v-spacer>
        <span>&copy; 2017</span>
      </v-footer>
    </v-app>
  </div>
</template>

<script>
  export default {
    name: 'vuetify-electron',
    data: () => ({
      clipped: false,
      drawer: true,
      ferrovia: 'EFC',
      lingua: 'Portugues',
      tema: 'Claro',
      fixed: false,
      items: [
        { icon: 'apps', title: 'Welcome', to: '/' },
        { icon: 'bubble_chart', title: 'Inspire', to: '/inspire' }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    })
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Roboto:300,400,500,700|Material+Icons');
  /* Global CSS */
</style>
