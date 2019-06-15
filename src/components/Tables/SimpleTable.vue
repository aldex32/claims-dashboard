<template>
  <div>
    <md-table v-model="users" :table-header-color="tableHeaderColor">
      <md-table-row slot="md-table-row" slot-scope="{ item }" @click.native="userPage()">
        <md-table-cell md-label="Username">{{ item.username }}</md-table-cell>
        <md-table-cell md-label="Name">{{ item.name }}</md-table-cell>
        <md-table-cell md-label="Email">{{ item.email }}</md-table-cell>
        <md-table-cell md-label="Phone">{{ item.phone }}</md-table-cell>
        <md-table-cell md-label="Claims">{{ item.claims }}</md-table-cell>
        <md-table-cell md-label="City">{{ item.city }}</md-table-cell>
      </md-table-row>
    </md-table>
  </div>
</template>

<script>
export default {
  name: "simple-table",
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
          username: "d.rice",
          phone: "+31 6 12345678",
          email: "d.rice@email.me",
          name: "Dakota Rice",
          claims: "5",
          city: "Haarlem"
        },
        {
          username: "m.hopper",
          phone: "not consented",
          email: "m.hopper@email.me",
          name: "Minerva Hooper",
          claims: "5",
          city: "Haarlem"
        },
        {
          username: "s.rodriguez",
          phone: "+31 6 12345678",
          email: "s.rodriguez@email.me",
          name: "Sage Rodriguez",
          claims: "4",
          city: "Haarlem"
        },
        {
          username: "p.chaney",
          phone: "+31 6 12345678",
          email: "p.chaney@email.me",
          name: "Philip Chaney",
          claims: "3",
          city: "Haarlem"
        },
        {
          username: "d.greene",
          phone: "+31 6 12345678",
          email: "d.greene@email.me",
          name: "Doris Greene",
          claims: "2",
          city: "Haarlem"
        },
        {
          username: "m.porter",
          phone: "+31 6 12345678",
          email: "m.porter@email.me",
          name: "Mason Porter",
          claims: "1",
          city: "Haarlem"
        }
      ]
    };
  },
  methods: {
    userPage: () => {
      window.location.href = "#/user";
    }
  }
};
</script>
