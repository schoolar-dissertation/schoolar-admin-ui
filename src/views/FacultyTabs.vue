<template>
  <auth-layout>
    <div class="container mt-2">
      <div class="card">
        <div class="card-body">
          <ul class="nav nav-tabs">
            <li class="nav-item">
              <span
                class="nav-link"
                @click="tab = 1"
                :class="{ active: tab === 1 }"
                >Groups</span
              >
            </li>
            <li class="nav-item">
              <span
                class="nav-link"
                @click="tab = 2"
                :class="{ active: tab === 2 }"
                >Subjects</span
              >
            </li>
          </ul>
          <div class="tab-content p-5">
            <div
              class="tab-pane"
              :class="{ show: tab === 1, active: tab === 1 }"
              v-if="tab === 1"
            >
              <group-tab />
            </div>
            <div
              class="tab-pane"
              :class="{ show: tab === 2, active: tab === 2 }"
              v-if="tab === 2"
            >
              <subject-tab />
            </div>
          </div>
        </div>
      </div>
    </div>
  </auth-layout>
</template>

<script>
import AuthLayout from '@/layouts/AuthLayout.vue';

import GroupTab from '@/containers/GroupTab.vue';
import SubjectTab from '@/containers/SubjectTab.vue';

export default {
  data: () => ({
    tab: 1
  }),
  components: {
    AuthLayout,
    GroupTab,
    SubjectTab
  }
};
</script>
