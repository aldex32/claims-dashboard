<template>
  <div>
    <md-table v-model="users" :table-header-color="tableHeaderColor">
      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell md-label="ID" @click.native="claimDetails()">{{ item.id }}</md-table-cell>
        <md-table-cell md-label="Username" @click.native="claimDetails()">{{ item.username }}</md-table-cell>
        <md-table-cell md-label="Category" @click.native="claimDetails()">{{ item.category }}</md-table-cell>
        <md-table-cell md-label="Title" @click.native="claimDetails()">{{ item.title }}</md-table-cell>
        <md-table-cell md-label="Neighbourhood" @click.native="claimDetails()">{{ item.neighbourhood }}</md-table-cell>
        <md-table-cell md-label="Location"><a :href="item.location" target="_blank">View</a></md-table-cell>
      </md-table-row>
    </md-table>
  </div>
</template>

<script>
export default {
  name: "ordered-table",
  props: {
    tableHeaderColor: {
      type: String,
      default: ""
    }
  },
  data() {
    return {
      selected: [],
      users: [
        {
          id: 1,
          username: "Dakota Rice",
          category: "Car",
          title: "Inappropriate parking",
          neighbourhood: "Oude stad",
          location:
            "https://www.google.it/maps/place/Oude+Stad,+Haarlem/@52.3831581,4.62727,15z/data=!3m1!4b1!4m5!3m4!1s0x47c5ef6c3bed21db:0xe01940c545e32d87!8m2!3d52.3851244!4d4.6359168"
        },
        {
          id: 2,
          username: "Minerva Hooper",
          category: "Car",
          title: "Yet another genius",
          neighbourhood: "Schalkwijk",
          location:
            "https://www.google.it/maps/place/Schalkwijk,+Haarlem/@52.3550158,4.6208935,13z/data=!3m1!4b1!4m5!3m4!1s0x47c5e5ffdf64a965:0xe2adbac949e1eac1!8m2!3d52.3580837!4d4.6555225"
        },
        {
          id: 3,
          username: "Sage Rodriguez",
          category: "Car",
          title: "Dangerous parking",
          neighbourhood: "Duinwijk",
          location:
            "https://www.google.it/maps/place/Duinwijk,+Haarlem/@52.3799142,4.5970618,14z/data=!3m1!4b1!4m5!3m4!1s0x47c5ef1905cec8ff:0x1c1bf730bbf93b17!8m2!3d52.3808509!4d4.6087539"
        },
        {
          id: 4,
          username: "Philip Chaney",
          category: "Bike",
          title: "Speechless",
          neighbourhood: "Haarlem-Oost",
          location:
            "https://www.google.it/maps/place/Haarlem-Oost,+Haarlem/@52.3898797,4.6285839,13z/data=!3m1!4b1!4m5!3m4!1s0x47c5e586f0f53c51:0x38bcc489fb14689!8m2!3d52.3813111!4d4.6650451"
        }
      ]
    };
  },
  methods: {
    claimDetails: () => {
      window.location.href = "#/claim";
    }
  }
};
</script>
