<template>
  <b-card no-body class="app-card">
    <b-row no-gutters>
      <b-col md="4" class="img-wrap">
        <b-card-img :src="news.img" alt="" class="rounded-0"></b-card-img>
      </b-col>
      <b-col md="8">
        <div class="card-body">
          <div v-if="!editingTitle">
            <b-badge
              class="app-badge"
              variant="success"
              @click="editingTitle = true"
              >Редактировать</b-badge
            >
            <h4 class="card-title">
              {{ news.title }}
            </h4>
          </div>
          <div v-else>
            <b-badge
              class="app-badge"
              variant="success"
              @click="editingTitle = false"
              >Сохранить</b-badge
            >
            <b-form-input
              id="input-1"
              v-model="news.title"
              type="email"
              required
              placeholder="Enter email"
            ></b-form-input>
          </div>
          <div v-if="!editingDescription">
            <b-badge
              class="app-badge"
              variant="secondary"
              @click="editingDescription = true"
              >Редактировать</b-badge
            >
            <div class="card-text" v-html="news.description"></div>
          </div>
          <div v-else>
            <b-badge
              class="app-badge"
              variant="secondary"
              @click="editingDescription = false"
              >Сохранить</b-badge
            >
            <vue-editor v-model="news.description"></vue-editor>
          </div>
        </div>
      </b-col>
    </b-row>
  </b-card>
</template>

<script>
import { VueEditor } from 'vue2-editor';

export default {
  data: () => ({
    editingTitle: false,
    editingDescription: false,
    editor: null
  }),
  props: {
    news: {
      required: true,
      type: Object
    }
  },
  components: { VueEditor }
};
</script>

<style></style>
