<template>
  <div class="container">
    <div class="card">
      <div class="front side">
        <Logo />
      </div>
      <div class="back side">
        <h1 class="title">Mario Cao</h1>
        <hr />
        <div class="social">
          <a href="https://twitter.com/cao_mario">
            <fa :icon="['fab', 'twitter']" />
          </a>
          <a href="https://github.com/mariocao">
            <fa :icon="['fab', 'github']" />
          </a>
          <a href="https://www.linkedin.com/in/mariocao/">
            <fa :icon="['fab', 'linkedin']" />
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">

* {
  box-sizing: border-box;
}

.container {
  perspective: 800px;
  min-width: 320px;

  /* Styling */
  color: #fff;

  /* Center it */
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.card {
  /* Styling */
  width: 480px;
  height: 240px;
  background: rgb(20, 20, 20);
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16), 0 3px 6px rgba(0, 0, 0, 0.23);

  /* Card flipping effects */
  transform-style: preserve-3d;
  transition: 0.6s;
}
.side {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  /* Fix Chrome rendering bug */
  transform: rotate(0deg) translateZ(1px);
}

/* Flip the card on hover */
.container:hover .card,
.back {
  transform: rotateY(-180deg) translateZ(1px);
}

/* Make semi-responsive */
@media (max-width: 500px) {
  .card {
    transform: scale(0.8);
  }
  .container:hover .card {
    transform: scale(0.8) rotateY(-180deg) translateZ(1px);
  }
}

/* Front styling */
.front {
  /* Center the name + outline (almost) */
  text-align: center;
  display: flex;
  align-items: center;
  height: 100%;
}

/* Back styling */
.back {
  padding: 50px;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.title {
  // outline: 1px solid #19f6e8;
  text-transform: uppercase;
  font-family: "Raleway";
  font-size: 2em;
  font-weight: normal;
  letter-spacing: 10px;
}

hr {
  border: 0;
  border-top: 1px solid #19f6e8;
  margin: 0px 120px;
}

.social {
  color: fade-out(#fff, 0.6);
  a {
    color: gray;
    font-size: 1.8em;
    padding: 10px;
    &:hover {
      color: fade-out(#fff, 0.2);
    }
  }
}
</style>
