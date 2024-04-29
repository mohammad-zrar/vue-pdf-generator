<template>
  <!-- Inline style example -->
  <div class="m-4"></div>
  <div class="border-solid bottom-2 border-black">
    <div
      id="element-to-print"
      class="a4-container h-auto"
      style="margin: 0 auto"
    >
      <div class="text-center">
        <HelloWorld />
      </div>

      <div class="mx-auto w-48 mt-4">
        <!-- Inline style example -->
        <img class="w-48" src="./assets/vue.svg" alt="" style="width: 100%" />
      </div>
    </div>
  </div>

  <div class="mt-4 mx-auto text-center">
    <button
      class="border-none rounded-md p-1 bg-slate-500 text-cyan-50 mt-1 mb-8"
      @click="exportToPdf"
    >
      Export to PDF
    </button>
  </div>
</template>

<script lang="ts" setup>
import HelloWorld from "./components/HelloWorld.vue";
import html2pdf from "html2pdf.js";
const exportToPdf = () => {
  html2pdf(document.getElementById("element-to-print"));
  // html2pdf().from(document.body).save();
  // html2pdf().from(document.documentElement).save();
  // html2pdf().from(document.documentElement).set({ format: "A4" }).save();
  // html2pdf()
  //   .from(document.documentElement)
  //   .set({
  //     format: "A4",
  //     margin: [20, 20, 20, 20], // [top, right, bottom, left]
  //   })
  //   .save();
};
</script>
<style>
.a4-container {
  width: 210mm; /* A4 width in millimeters */
  height: auto; /* A4 height in millimeters */
  /* Optionally, you can add additional styles like border and margin */
  /* Border for visualization */
  margin: 0 auto; /* Centering the div */
  page-break-after: always;
}
</style>
