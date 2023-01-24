<script>
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import { getAnalytics } from "firebase/analytics";
import { getDatabase, ref, set, onValue, get } from "firebase/database";

// Configuration
const firebaseConfig = {
  apiKey: "AIzaSyDH6X1WuGkO2WP6320JhaoFrAVgjsxG208",
  authDomain: "bowman-1aa81.firebaseapp.com",
  projectId: "bowman-1aa81",
  storageBucket: "bowman-1aa81.appspot.com",
  messagingSenderId: "941433140198",
  appId: "1:941433140198:web:02b1eb12ad1e22976c5c27",
  measurementId: "G-7EBJDJH4Y7"
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
const dbRef = ref(getDatabase());

async function readScoreboard() {
  return get(child(dbRef, `users/${userId}`)).then((snapshot) => {
    if (snapshot.exists()) {
      console.log(snapshot.val());
    } else {
      console.log("No data available");
    }
  }).catch((error) => {
    console.error(error);
  });
}
</script>

<template>

</template>

<style>


</style>