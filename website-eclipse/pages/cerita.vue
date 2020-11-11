<template>
  <div>
    <h1>
      <div class="text-h2 text-center font-weight-bold mb-3">
        <number
          class="bold transition"
          ref="number1"
          :class="{ scaleBig: scaleClass }"
          :from="numberFrom"
          :to="numberTo"
          :duration="duration"
          easing="Power2.easeOut"
        />
      </div>
    </h1>
  </div>
</template>

<script>
export default {};
</script>