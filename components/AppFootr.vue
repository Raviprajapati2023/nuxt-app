<template>
  <footer class="footer">
    <div
      class="footer-main-area bg-slate-900 text-white"
      style="background-image: url('/img/footer-bg-2.png')"
    >
      <div class="container p-8 py-16 max-w-7xl mx-auto">
        <a  class="flex gap-4 my-4">
            <img
              src="https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1662375671324-image_picker888690444996149863.jpg"
              width="50"
              height="50"
              alt="Float UI logo"
            />
          <span class="mx-2 text-2xl text-center  my-auto text-yellow-500 font-semibold">Antrie</span>
          </a>
        <div class="flex">
          
          <div class="xl:w-7/12 md:w-7/12 sm:w-full">
            <div class="widget footer-widget text-gray-400 text-mg">
              <!--	<img src="images/footer_logo.png" alt="" class="mrb-20">-->
              <h5
                class="widget-title text-yellow-500 mb-2 text-2xl font-semibold"
              >
                Address
              </h5>
              <address
                class="mb-6"
                v-for="(branch, index) in branchList"
                :key="index"
              >
                <p class="mb-6 text-md text-white">
                  {{ branch.address.addLineOne }} ,{{
                    branch.address.landmark
                  }},{{ branch.address.city }},Pin Code-{{
                    branch.address.pinCode
                  }}, {{ branch.address.state }}, {{ branch.address.country }}
                </p>
              </address>
              <div class="text-yellow-500 mb-2 text-xl font-semibold">
                Phone Number
              </div>
              <span
                class="flex text-md text-white flex flex-nowrap w-auto gap-2 "
                v-for="(branch, index) in branchList"
                :key="index"
              >
                {{ branch.contactNumber }}
              </span>
             
            </div>
          </div>
          <div class="ml-8 xl:w-4/12 md:w-4/12 sm:w-full">
            <div class="widget footer-widget pl-8">
             
                <h5
                class="widget-title relative text-yellow-500 mb-10 text-2xl font-medium"
              >
                Quicks Links
              </h5>
              
              
              <ul class="footer-widget-list text-white space-y-3 text-md mx-auto">
                <li>
                  <a href="#Facilities">Facilities</a>
                </li>
                <li><a href="#Courses">Offered Courses</a></li>
                <li><a href="#Faculties">Faculties</a></li>
                <li><a href="#Batches">Featured Batches</a></li>
                <li><a href="#Reviews">Reviews</a></li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>
<script setup>
defineProps({
  branchList: Array,
});
</script>
<style scoped>
.widget-title:after {
  position: absolute;
  content: "";
  height: 4px;
  width: 58px;
  left: 0;
  bottom: -15px;
  background: linear-gradient(45deg, #ec3237, #ed2d33) !important;
  border-radius: 6px;
}

.footer-widget-list li a:hover {
  border-bottom: 1px solid #ed2d33;
}
</style>
address : {country: "India", state: "Bihar", district: null, city: "Patna",
pinCode: "800020",…} addLineOne : "B/173, Shruti Kunj" addLineTwo : null area :
"Kankarbagh" city : "Patna" country : "India" district : null landmark :
"Raghunath School" pinCode : "800020" state : "Bihar" contactNumber :
"9693243217" mainBranch : true officeTiming : "7:01 AM 9:00 PM"
