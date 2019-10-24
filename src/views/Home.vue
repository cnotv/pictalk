<template>
  <a-auto-complete
    :dataSource="dataSource"
    style="width: 90vw"
    placeholder="Search a term"
    :filterOption="filterOption"
  />
</template>

<script>
// @ is an alias to /src
export default {
  name: "home",
  data() {
    return {
      dataSource: ["eat", "sleep", "shower"]
    };
  },
  methods: {
    filterOption(input, option) {
      return (
        option.componentOptions.children[0].text
          .toUpperCase()
          .indexOf(input.toUpperCase()) >= 0
      );
    }
  }
};
</script>
