<template>
  <div class="py-10 px-0 h-screen w-full" >
      <v-card class="mb-20">
        <v-toolbar class="color font-sans text-white/90">
          <template v-slot:extension>
            <v-tabs
              v-model="tab"
              centered
              stacked
              class="justify-center m-auto " 
            >
              <v-tab
                v-for="item in items"
                :key="item.key"
                :value="item.key"
              >
              <div class="flex justify-center items-center">
                <v-icon>{{ item.icon }}</v-icon>
                <h3 class="text-2xl">
                  {{ item.key }}
                </h3>
              </div>
              <p class="">
                {{ item.title }}
              </p>
              </v-tab>
            </v-tabs>
          </template>
        </v-toolbar>

        <v-window v-model="tab">
          <v-window-item
            v-for="item in items"
            :key="item.key"
            :value="item.key"
          >
            <div flat class="color py-10 flex flex-row justify-center gap-x-4 ">
              <v-card
                v-for="(card) in item.cards"
                :key="card.title"
                width="400"
                :title="card.title"
                :subtitle="item.title"
                :text="item.text"
                class="card-color border-card rounded-md text-white/90"
                >

                <p 
                v-if="card.text!=='select'"
                class="mx-4 mt-10"
                >{{ card.text }}</p>
                <p class="mx-4 my-4  text-4xl text-white/90">{{ card.price }}</p>
                <v-btn class="btn mx-4">
                  Get started
                </v-btn>
                <v-list
                  :items="card.perks"
                  item-props
                  class="card-color text-white/90 mt-8"
                  >
                </v-list>
              </v-card>
            </div>
          </v-window-item>
        </v-window>
      </v-card>
 
</div>
</template>
<style scoped>
.color{
  background-color: #0E2F6C;
}
.card-color{
  background-color: #34394D;
}
.border-card{
  border: 1px solid rgba(255, 255, 255, 0.5);
}
.btn{
  color: #34394D;
  background-color: #9CC0C6;
}
</style>
<script >
import {items} from "../fixtures/tabs"; 
 export default {
    data () {
      return {
        tab: false,
        items
       }
    }
  }
</script>
