<template>
  <button @click="filtered = !filtered">
    Filter Apartments
  </button>

  <div v-if="!filtered">
    <Apartment
      v-for="(apartment, index) in apartments"
      :key="index"
      :apartmentDetails="apartment"
      @saleChange="handleSaleChange(index)"
      class="apartmentListing"
    />
  </div>
  <div v-else>
    <Apartment
      v-for="(apartment, index) in filteredApartments"
      :key="index"
      :apartmentDetails="apartment"
      @saleChange="handleSaleChange(index)"
      class="apartmentListing"
    />
  </div>
  boo

  <!-- Create Apartment component, with mouseover and mouseleave functions - should show apartment details and
    arrangements when mouse is over it-->
</template>

<script>
import Apartment from "./Apartment";
export default {
  name: "HelloWorld",
  props: {},
  components: {
    Apartment,
  },
  data() {
    return {
      visible: false,
      x: 0,
      y: 0,
      filtered: false,
      apartments: [
        {
          location: "Vake",
          goodLocation: true,
          catchyName: "Cool Apartment in Great Neighborhood",
          spaceInSquareMeters: 45,
          image:
            "https://cdn.home-designing.com/wp-content/uploads/2014/06/studio-apartment-floor-plans.jpeg",
          onSale: false,
        },
        {
          location: "Sanzona",
          goodLocation: false,
          catchyName: "Cheap Apartment in Up And Coming Neighborhood",
          spaceInSquareMeters: 75,
          image:
            "https://i.pinimg.com/originals/27/39/11/273911e4e5babcfa2348a556fe1300c1.jpg",
          onSale: false,
        },
        {
          location: "Saburtalo",
          goodLocation: true,
          catchyName: "Perfect Budget Option in Central Neighborhood",
          spaceInSquareMeters: 60,
          image:
            "https://www.smalldesignideas.com/wp-content/uploads/2016/07/3dfloorplans_003.jpg",
          onSale: true,
        },
        {
          location: "Gldani",
          goodLocation: false,
          catchyName: "Solid Apartment in Artsy Neighborhood",
          spaceInSquareMeters: 82,
          image:
            "https://homededicated.com//wp-content/uploads/2018/02/Plan-of-small-one-bedroom-apartment.jpg",
          onSale: false,
        },
        {
          location: "Bagebi",
          goodLocation: true,
          catchyName: "Apartment in Solid Neighborhood for Cheap Price",
          spaceInSquareMeters: 55,
          image:
            "https://cdngeneral.rentcafe.com/dmslivecafe/3/565342/p0574788_UnitS3_3DforWeb_new_FloorPlanNew.jpg",
          onSale: false,
        },
      ],
    };
  },
  computed: {
    filteredApartments() {
      return this.apartments.filter((apartment) => apartment.onSale == true);
    },
  },
  methods: {
    handleMouseOver() {
      console.log("wohoo some attention!! nice!");
    },
    handleMouseLeave() {
      console.log("me so horny me love you long time!");
    },
    handleDoubleClick() {
      console.log("You should double click my ass");
    },
    handleMouseMove(e) {
      this.x = e.offsetX;
      this.y = e.offsetY;
    },
    handleSaleChange(index) {
      this.apartments[index].onSale = !this.apartments[index].onSale;
      console.log(this.apartments);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
.apartmentListing {
  border-top: 2px solid grey;
  background: rgb(255, 243, 220);
  margin-top: 1rem;
}
</style>
