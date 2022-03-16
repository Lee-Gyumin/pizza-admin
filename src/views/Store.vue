<template>
  <v-container fluid>
    <v-row>
      <v-col
        v-for="(item, index) in items"
        :key="index"
        cols="auto"
        sm="4"
        md="4"
        lg="2"
        xl="2"
      >
        <v-card>
          <!-- <v-img
            class="white--text align-end"
            height="150px"
            src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
          > -->
          <v-card-title class="c-title">
            <tr>
              <td>{{ item.number }}번 테이블</td>
              <td>{{ item.totalPrice }}원</td>
            </tr>
            <v-card-subtitle class="pb-0">
              {{ item.time }} 입장
            </v-card-subtitle>
          </v-card-title>

          <!-- </v-img> -->

          <v-card-text class="text--primary c-text">
            <tr
              v-for="(menu, index) in item.menu"
              :key="index"
              class="menu-info"
            >
              <td>{{ menu.name }}*{{ menu.ea }}</td>
              <td>{{ menu.price * menu.ea }}원</td>
            </tr>
          </v-card-text>

          <v-card-actions class="justify-end">
            <v-btn color="orange">
              자세히보기
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  data: () => ({
    items: [
      {
        number: "1",
        totalPrice: 91000,
        time: "11:20",
        menu: [
          { name: "닭도리탕", price: 24000, ea: 1 },
          { name: "제육볶음", price: 8000, ea: 3 },
          { name: "계란찜", price: 5000, ea: 2 },
          { name: "라면", price: 3000, ea: 2 },
          { name: "참이슬", price: 4000, ea: 3 },
          { name: "카스", price: 5000, ea: 3 }
        ]
      },
      {
        number: "2",
        totalPrice: 38000,
        time: "14:20",
        menu: [
          { name: "아구찜", price: 22000, ea: 1 },
          { name: "제육볶음", price: 8000, ea: 2 }
        ]
      }
    ]
  })
};
</script>
<style scoped>
.c-title {
  border-bottom: 2px solid gray;
}
.c-title tr {
  width: 100%;
  display: flex;
  justify-content: space-between;
}
.v-card__title + .v-card__subtitle,
.v-card__title + .v-card__text {
  padding: 16px;
}
.v-card__subtitle {
  padding: 0;
}
.menu-info {
  display: flex;
  width: 100%;
  justify-content: space-between;
}
</style>
