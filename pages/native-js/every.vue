<template>
  <CodeBox v-model="code" />
</template>

<script>
export default {
  layout: 'center',
  data: () => ({
    code: `Array.prototype.customEvery = function (callback, context) {
  for (let i = 0; i < this.length; ++i) {
    if (!callback.call(context, this[i], i, this)) {
      return false
    }
  }

  return true
}

// tests
let passed = [12, 5, 8, 130, 44].customEvery((element, index, arr) => (element >= 10))
console.log(passed) // false

passed = [12, 54, 18, 130, 44].customEvery((element, index, arr) => (element >= 10))
console.log(passed) // true

passed = [12, 54, 18, 130, 44].customEvery((element, index, arr) => (element >= 13))
console.log(passed) // false`
  })
}
</script>
