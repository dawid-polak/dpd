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

     fetch("https://api-preprod.dpsin.dpdgroup.com:8443/shipping/v1/login", requestOptions)
          .then((response) => response.text())
          .then((result) => console.log(result))
          .catch((error) => console.log("error", error));
};
</script>

<template>
     <button @click="handle_send">Send request</button>
</template>
