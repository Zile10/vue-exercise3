<template>
  <div class="card bg-light text-dark rounded-0" style="width: 18rem;">
    <img :src="imgSrc" class="card-img-top" alt="men's cotton tshirt blue">
    <div class="card-body">
      <h5 class="card-title" style="text-transform: capitalize;">{{ name }}</h5>
      <h6>Price: R {{ price }}.00</h6>

      <!-- Button trigger modal -->
      <button type="button" class="btn btn-primary" data-bs-toggle="modal" :data-bs-target="'#productModal-'+id">
        View More...
      </button>
      <button type="button" class="btn btn-primary" onclick="addToCheckout(1)">Add to Checkout</button>

      <!-- Modal -->
      <div class="modal fade" :id="'productModal-'+id" tabindex="-1" :aria-labelledby="'productModal-'+id" aria-hidden="true" style="text-align: center;">
        <div class="modal-dialog">
          <div class="modal-content">
            <div class="modal-header">
              <h1 class="modal-title fs-5" :id="'productModal-'+id+'Label'">{{ name }}</h1>
              <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
            </div>
            <div class="modal-body flex-column">
              <img :src="imgSrc" class="card-img-top" alt="men's cotton tshirt blue">
              <h6>Price:    R{{ price }}</h6>
              <h6>In stock:    100</h6>
              <h6>Colour:    blue</h6>
            </div>
            <div class="modal-footer">
              <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
              <button type="button" class="btn btn-primary" onclick="addToCheckout(`${id}`)">Add to Checkout</button>
            </div>
          </div>
        </div>
      </div>

    </div>
  </div>

</template>

<script>
export default {
  props: ['name', 'id', 'price', 'imgSrc']
}
</script>

<style>
  .card {
  color: #fff;
  height: 29rem;
}
.card>img {
  /* width: 80%; */
  /* height: 20rem; */
  margin: auto;
}

.modal-body{
  display: flex;
}

.modal img {
  margin: auto;
  width: 50%;
}
.modal-body form {
  width: 100%;
}
.modal-body form input, .modal-body form textarea {
  width: 100%;
}
.modal-body form label {
  padding-top: 10px;
  padding-bottom: 5px;
  font-weight: bold;
}

</style>