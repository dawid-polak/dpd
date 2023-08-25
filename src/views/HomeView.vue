<script setup>
const handle_send = async () => {
     let myHeaders = new Headers();
     myHeaders.append("X-DPD-BUCODE", "021");
     myHeaders.append("X-DPD-LOGIN", "test");
     myHeaders.append("X-DPD-PASSWORD", "thetu4Ee");

     let formdata = new FormData();

     let requestOptions = {
          method: "POST",
          headers: myHeaders,
          body: formdata,
          redirect: "follow",
     };

     fetch("https://dpdservicesdemo.dpd.com.pl/DPDPackageObjServicesService/DPDPackageObjServices?wsdl", requestOptions)
          .then((response) => response.text())
          .then((result) => console.log(result))
          .catch((error) => console.log("error", error));
};
</script>

<template>
     <button @click="handle_send">Send request</button>
</template>
