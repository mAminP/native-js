<template>
  <CodeBox v-model="code" />
</template>

<script>
export default {
  layout: 'center',
  data: () => ({
    code: `Array.prototype.customForEach = function (callback) {
    for (let i = 0; i < this.length; i++) {
        if (Object.hasOwnProperty.call(this, i)) {
            callback(this[i], i, this);
        }
    }
};

// test
const arr = ['Mohammad','Amin','Pasban'];

arr.customForEach((word)=>{
    console.log(word)
})
// output :

// Mohammad
// Amin
// Pasban
`
  })
}
</script>
