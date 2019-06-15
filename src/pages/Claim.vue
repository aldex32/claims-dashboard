<template>
  <div class="content">
    <div class="md-layout">
      <div class="md-layout-item md-medium-size-100 md-size-66">
        <md-card>
          <md-card-header data-background-color="green">
            <h4 class="title">Inappropriate parking</h4>
          </md-card-header>

          <md-card-content>
            <div class="md-layout-item md-size-100">
              <md-field maxlength="5">
                <label>User</label>
                <md-textarea v-model="user" md-autogrow></md-textarea>
              </md-field>
            </div>
            <div class="md-layout-item md-size-100">
              <chart-card
                :chart-data="picture.data"
                :chart-options="picture.options"
                :chart-type="'Line'"
                :chart-image="picture.image"
                data-background-color="blue"
              >
                <template slot="footer">
                  <div class="stats">
                    <md-icon>access_time</md-icon>
                    reported 4 minutes ago
                  </div>
                </template>
              </chart-card>
            </div>
            <div class="md-layout-item md-size-100">
              <md-field maxlength="5">
                <label>Location</label>
                <md-icon>location_on</md-icon>
                <md-textarea v-model="location" md-autogrow></md-textarea>
              </md-field>
            </div>
            <div class="md-layout-item md-size-100">
              <md-field maxlength="5">
                <label>Description</label>
                <md-textarea v-model="description" md-autogrow></md-textarea>
              </md-field>
            </div>
          </md-card-content>
        </md-card>
      </div>
    </div>
  </div>
</template>

<script>
import { ChartCard } from "@/components";

export default {
  components: {
    ChartCard
  },
  data() {
    return {
      picture: {
        data: {
          labels: ["M", "T", "W", "T", "F", "S", "S"],
          series: [[12, 17, 7, 17, 23, 18, 38]]
        },
        options: {
          lineSmooth: this.$Chartist.Interpolation.cardinal({
            tension: 0
          }),
          low: 0,
          high: 50, // creative tim: we recommend you to set the high sa the biggest value + something for a better look
          chartPadding: {
            top: 0,
            right: 0,
            bottom: 0,
            left: 0
          }
        },
        image: require("@/assets/img/car1.jpg")
      },
      user: "d.rice",
      description:
        "Car parked on the walking path by the cross road, blocking the view to check on coming vehicles.",
      location: "Central Station, Haarlem"
    };
  }
};
</script>
