<script>
    export let p;
    export let x;
    export let y;
    export let z;
</script>

<div class="box-frame">
    <div style="transform: perspective({p}px) rotateX({x}deg) rotateY({y}deg) rotateZ({z}deg)" class="box"></div>
</div>

<style>
  .box-frame {
    margin-left: 36px;
    padding: 50px;
    border: 1px solid #8d81f3;
  }
  .box {
    width: 150px;
    height: 150px;
    background: #8d81f3;
  }

  @media (max-width: 1023px) {
      .box-frame {
          margin: 2rem 0;
      }
  }
</style>