<template>
  <div v-if="lang === false">
  <v-card
   class="mx-auto overflow-hidden"  
   style="height: 1050px"
    >

    <v-app-bar
      color="deep-purple accent-4"
      dark
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Welcome</v-toolbar-title>

      <v-spacer></v-spacer>
      <v-btn  style="background-color: white; color: black;"
              @click="lang = !lang"
              color="primary"
              dark
            >
            Ar
      </v-btn>
    </v-app-bar>
    <v-navigation-drawer
      v-model="drawer"
      
      temporary
      >
      <v-list-item>
        <v-list-item-avatar>
          <v-img src="https://randomuser.me/api/portraits/men/78.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>John Leider</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item
          v-for="item in items1"
          :key="item.title"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    
    
  </v-card>
  </div>
  <div v-else-if ="lang === true">
  <v-card
   class="mx-auto  overflow-hidden "  
   style="height: 1050px; "
    >

    <v-app-bar
      color="deep-purple accent-4"
      dark
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" 
          style="position: absolute; right: 10px"

      ></v-app-bar-nav-icon>

      <v-toolbar-title
            absolute right
            style="position: absolute; right: 60px"
        >مرحبا</v-toolbar-title>
      <v-btn  @click="lang = !lang"
              style="background-color: white; color: black;"
              color="primary"
              dark
            >
            En
      </v-btn>
      <v-spacer></v-spacer>
      
    </v-app-bar>
    <v-navigation-drawer
      v-model="drawer"
      absolute 
      right
      temporary
      >
      <v-list-item>
        <v-list-item-avatar>
          <v-img src="https://randomuser.me/api/portraits/men/78.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>John Leider</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item
          v-for="item in items2"
          :key="item.title"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    
    
  </v-card>
  </div>
</template>
<script>
export default {

  
  name: 'App',
  lang:true,
  components: {
    
  },
  props:{
    lang: {
      type: Boolean
    }
  }
  
  ,
  data: () => ({
      lang:true,
      drawer: false,  
      group: null,
      items1: [
          { title: 'Home', icon: 'mdi-view-dashboard' },
          { title: 'About', icon: 'mdi-forum' },
        ],
      items2: [
          { title: 'الصفحة الرئيسية', icon: 'mdi-view-dashboard' },
          { title: 'معلومات عنا', icon: 'mdi-forum' },
        ],
      
    }),
    watch: {
      group () {
      },
    }



};
</script>

<style>
select {
  background-color : white;
  color: black;
}


</style>