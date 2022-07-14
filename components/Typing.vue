<template>
  <div>
    <span id="AboutDevTypeText" class="typing"></span>
  </div>
</template>

<script>
var data = [
  {
    AboutDevTypeText: "A digital agency focused on web. ",
  },
];

export default {
  mounted() {
    var allElements = document.getElementsByClassName("typing");
    for (var j = 0; j < allElements.length; j++) {
      var currentElementId = allElements[j].id;
      var currentElementIdContent = data[0][currentElementId];
      var element = document.getElementById(currentElementId);
      var devTypeText = currentElementIdContent;

      // type code
      var i = 0,
        isTag,
        text;
      (function type() {
        text = devTypeText.slice(0, ++i);
        if (text === devTypeText) return;
        element.innerHTML = text + `<span class='blinker'>&#32;</span>`;
        var char = text.slice(-1);
        if (char === "<") isTag = true;
        if (char === ">") isTag = false;
        if (isTag) return type();
        setTimeout(type, 60);
      })();
    }
  },
};
</script>

<style lang="scss">
span {
  color: #41b883;
  font-family: monospace;
}

.blinker {
  opacity: 1;
  margin-bottom: -2px;
  height: 15px;
  margin-left: -5px;
  width: 0;
  border-left: 15px solid #41b883;
  animation: blinker 0.9s steps(2, start) infinite;
}

@keyframes blinker {
  to {
    visibility: hidden;
  }
}
</style>