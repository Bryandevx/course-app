<template>
  <div class="ui stackable three column grid">
    <div class="colum" v-for="(course, index) in courses" :key="index">
      <div class="ui-container">
        <div class="ui card">
          <div class="image">
            <img :alt="course.alt" :src="require(`@/assets/${course.img}`)" />
          </div>
          <div class="content">
            <a class="header">{{ course.name }}</a>
            <div class="meta">
              <span class="date">{{ course.created }}</span>
            </div>
            <div class="description">
              {{ course.description }}
            </div>
            <div class="price">
              <strong>Cost ${{ course.price }}</strong>
            </div>
          </div>
          <div class="extra content">
            <a>
              <i class="user icon"></i>
              {{ course.maxStudents }} fields available
            </a>
            <pre><code>{{course.id}}</code></pre>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { courses } from "../api";
export default {
  name: "ShowCourses",
  data() {
    return {
      courses: null,
    };
  },
  mounted() {
    this.courses = courses;
    console.log(this.courses);
  },
  methods: {},
  computed: {
    getCourses() {
      return "";
    },
  },
};
</script>

<style lang="scss" scoped>
</style>