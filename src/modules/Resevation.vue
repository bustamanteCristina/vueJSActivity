<template>
  <div>
    <div id="cardbody">
      <b-card no-body class="overflow-hidden" style="max-width: 1000px;">
        <b-card-img id="images" :src="require('assets/bus.jpg')" class="rounded-0"></b-card-img>
        <b-img  id="driverimg" :src="require('assets/stdnt.png')" v-bind= "mainProps" rounded="circle" alt="Circle image"/>
        <hr id="hrColor">
        <b-card-text class="text-center">
            <p id="ceres">Ceres Liner</p>
            <hr>
          <a href="https://www.google.com/maps/@10.34379,123.9192341,15z" id="detail">route details</a>
          <p>Estimated Fare : ₱120.00 - ₱170.00</p>
          <b-btn id="button">Reserve</b-btn>
          <b-btn id="cancel">Cancel</b-btn>
          <b-nav id="passenger">Passenger</b-nav>

        </b-card-text>
      </b-card>
    </div>
  </div>
</template>

<style scoped lang="scss">
@import "assets/style.scss";
#cardbody {
  margin-left: $margin-left !important;
  margin-top: $margin-top !important;
}

#images {
  width: $dashwidth !important;
  height: $dashheight !important;
}
#ceres {
    text-align: left;
}
#button{
    margin-right: 300px;
}
#detail {
    margin-left: 800px;
    
}

</style>

<script>
export default {
  name: "card",
  data() {
    return {
      username: sessionStorage.getItem("Username"),
      mainProps: { blank: true, blankColor: '#777', width: 200, height:200, class: 'm1' }
    };
  }
};
</script>