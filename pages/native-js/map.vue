<template>
  <CodeBox v-model="code" />
</template>

<script>

export default {

  layout: 'center',
  data: () => ({
    code: `Array.prototype.customMap = function (callback) {
    const arr = []
    for (let i = 0; i < this.length; i++) {
        if (Object.hasOwnProperty.call(this, i))
            arr.push(callback(this[i], i, this))
    }
    return arr
}

// test
const arr = ['Mohammad', 'Amin', 'Pasban']
const arrResult = arr.customMap((word, index, arr) => {
    return word + " ;)"
})
console.log(arrResult) // [ 'Mohammad ;)', 'Amin ;)', 'Pasban ;)' ]

const nums = [1, 4, 9];
const numsResult = nums.customMap((num, index, arr) => {
    return Math.sqrt(num)
})
console.log(numsResult) // [ 1, 2, 3 ]
`
  })
}
</script>
