<script>
  let count = 0
  const increment = () => {
    count += 1
    alert("HelloWorld")
  }
</script>

<button on:click={increment}>
  count is {count}
</button>
