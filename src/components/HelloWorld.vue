<template>
  <v-container>
    <v-toolbar cols="5" lg="5" offset="4" color="#f5f5f5" flat>
      <v-item-group selected-class ="bg-green-darken-3 rounded-t-lg  text- " >
        <v-item v-slot="{ selectedClass, toggle}">
         <v-btn 
            style="text-transform: capitalize; font-size: 16px"
            :class="selectedClass"
            @click="toggle"
            
          >
          <v-icon>mdi-magnify</v-icon>
            Consulta individual
          </v-btn>
        </v-item> 
        <v-item v-slot="{ selectedClass, toggle}">
            <v-menu>
              <template v-slot:activator="{ props }">
                <v-btn v-bind="props"
                  :class="selectedClass"
                  @click="toggle"
                  style="text-transform: capitalize; font-size: 16px"
                >
                  <v-icon>mdi-account-cog-outline</v-icon>
                  Administración
                </v-btn>
              </template>
              <v-list>
                <v-list-item
                  v-for="(item, index) in items"
                  :key="index"
                  :value="index"
                >
                  <v-list-item-title>{{ item.title }}</v-list-item-title>
                </v-list-item>
              </v-list>
            </v-menu>
        </v-item>
        <v-item v-slot="{ selectedClass, toggle}">
         <v-btn
            :class="selectedClass"
            @click="toggle"
            style="text-transform: capitalize; font-size: 16px"
          >
          <v-icon>mdi-folder-text-outline</v-icon>
          Logs
          </v-btn>
        </v-item>
        <v-item v-slot="{ selectedClass, toggle}">
         <v-btn
            :class="selectedClass"
            @click="toggle"
            style="text-transform: capitalize; font-size: 16px"
          >
          <v-icon>mdi-export</v-icon>
          Salir
          </v-btn>
        </v-item>
      </v-item-group>   
    </v-toolbar>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      items: [
        { title: 'Mi usuario' },
        { title: 'Administrar usuarios' },
        { title: 'Administrar perfiles' },
        { title: 'Administrar clientes' },
      ],
    }),
  }
</script>

<style>
.selected-class {
  background-color: #00805D;
}
</style>