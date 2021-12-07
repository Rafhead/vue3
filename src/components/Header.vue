<template>
  <header>
		<div class="tabs">
      <a href="#">About</a>
      <a href="#">Jobs</a>
      <a href="#">Infrastructure</a>
    </div>
  </header>
</template>


<script>

</script>


<style>
header {
	background-color: wheat;
	position: sticky;
  height: 55px;
  margin-bottom: 10px;
}

.tabs {
  float: right;
}

a {
  float: left;
  color: black;
  text-align: center;
  padding: 10px;
  font-size: 18px; 
  border-radius: 4px;
  text-decoration: none;
  margin-top: 2px;
}

a:hover {
  background-color: gray;
  color: black;
}
</style>