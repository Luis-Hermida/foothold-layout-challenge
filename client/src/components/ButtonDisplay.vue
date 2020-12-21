<template>
  <div class="content">
    <div v-if="isOpen" class="actions-container">
      <v-card
        elevation="4"
        v-for="action in actions"
        :key="action.viewText"
        class="action-card"
      >
        <v-icon class="action-icon" size="30" v-bind:color="action.iconColor">
          {{ action.icon }}
        </v-icon>
        <p class="action-text">{{ action.viewText }}</p>
      </v-card>
    </div>
    <div class="toggle-container">
      <v-btn
        v-if="!isOpen"
        v-on:click="toggleActions"
        class="action-button"
        color="#63e5cd"
        elevation="4"
        fab
      >
        <v-icon size="40" color="#0e2d3f">mdi-plus</v-icon>
      </v-btn>
      <v-btn
        v-else
        v-on:click="toggleActions"
        class="action-button"
        color="#0e2d3f"
        elevation="4"
        fab
      >
        <v-icon size="40" color="#63e5cd">mdi-close</v-icon>
      </v-btn>
    </div>
  </div>
</template>

<script>
export default {
  name: "ButtonDisplay",
  data() {
    return {
      isOpen: false,
      actions: [
        {
          icon: "mdi-account-plus",
          iconColor: "#9ff5e8",
          viewText: "New intake",
        },
        {
          icon: "mdi-account-remove",
          iconColor: "#fcc7c5",
          viewText: "Discharge",
        },
        {
          icon: "mdi-map-marker",
          iconColor: "#ffc8ee",
          viewText: "Check in",
        },
        {
          icon: "mdi-map-marker-off",
          iconColor: "#9bdbff",
          viewText: "Check out",
        },
        {
          icon: "mdi-snowman",
          iconColor: "#cecef9",
          viewText: "New medication",
        },
        {
          icon: "mdi-clippy",
          iconColor: "#fdd686",
          viewText: "New treatment plan",
        },
        {
          icon: "mdi-needle",
          iconColor: "#fbcabc",
          viewText: "New incident",
        },
        {
          icon: "mdi-gift",
          iconColor: "#9cf8e7",
          viewText: "New calendar event",
        },
        {
          icon: "mdi-barrel",
          iconColor: "#9ddbfb",
          viewText: "New progress note",
        },
        {
          icon: "mdi-paw",
          iconColor: "#f8c7eb",
          viewText: "New group note",
        },
      ],
    };
  },
  methods: {
    toggleActions() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>

<style lang="scss" scoped>
.content {
  height: 90vh;
  width: 90vw;
  margin: 16px auto;
  padding: 4px;
  position: relative;
  overflow: auto;

  .actions-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-end;
    align-content: flex-end;
    max-width: 660px;
    height: 90%;
    overflow: auto;
    float: right;

    .action-card {
      display: flex;
      align-items: center;
      min-width: 240px;
      height: 60px;
      margin: 10px;
      border-radius: 10px;
      cursor: pointer;

      &:hover {
        box-shadow: 0px 6px 10px -2px rgba(0, 0, 0, 0.2),
          0px 6px 6px 0px rgba(0, 0, 0, 0.14),
          0px 2px 12px 0px rgba(0, 0, 0, 0.12) !important;
      }

      .action-icon {
        margin: 0 10px;
      }

      .action-text {
        margin: 0 5px;
        font-weight: 700;
      }
    }
  }

  .toggle-container {
    padding: 4px;
    position: absolute;
    bottom: 0;
    right: 0;
  }
}

@media (max-width: 600px) {
  .content {
    .actions-container {
      align-content: stretch;
    }
  }
}
</style>
