<script>
  export let item = {};
</script>

<style>
  .card {
    cursor: pointer;
    background-color: transparent;
    height: 300px;
    perspective: 1000px;
  }

  .card h1 {
    font-size: 25px;
    border-bottom: 1px #fff solid;
    padding-bottom: 10px;
    margin-bottom: 10px;
  }

  .card img {
    width: 100%;
    height: 300px;
    object-fit: cover;
  }

  .card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    transition: transform 0.8s;
    transform-style: preserve-3d;
  }

  .card:hover .card-inner {
    transform: rotateY(180deg);
  }

  .card-front,
  .card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
  }

  .card-back {
    background-color: #333;
    color: white;
    padding: 20px;
    transform: rotateY(180deg);
  }

  .card li {
    list-style: none;
    padding-bottom: 10px;
  }
</style>

<div class="card">
  <div class="card-inner">
    <div class="card-front">
      <img src={item.img} alt="" />
    </div>
    <div class="card-back">
      <h1>{item.name}</h1>
      <ul>
        <li>
          <strong>Actor Name:</strong>
          {item.portrayed}
        </li>
        <li>
          <strong>Nickname:</strong>
          {item.nickname}
        </li>
        <li>
          <strong>Birthday:</strong>
          {item.birthday}
        </li>
        <li>
          <strong>Status:</strong>
          {item.status}
        </li>
      </ul>
    </div>
  </div>
</div>
