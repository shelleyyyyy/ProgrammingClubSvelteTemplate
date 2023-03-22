<script>

    const clickMe = () => {
        alert("YOUR FAKE WEBSITE IS WORKING")
    }

    import { onMount } from 'svelte';
    import axios from 'axios';

    async function getData(url) {
        const response = await axios.get(url);
        return response.data;
    }

    let person = ""

    onMount(async () => {
        let data = await getData('http://localhost:5000/getData');
        person = data
    });

</script>

<h1 class="text-4xl font-bold text-center p-10">Programming Club Start</h1>

<div class="flex justify-center">
    <button on:click={clickMe} class="btn">Click Me</button>
</div>

<!-- <h1>{person.name}</h1>
<h1>{person.age}</h1> -->

<div class="flex justify-center p-10">
    <div class="card w-96 bg-base-100 shadow-xl">
        <figure><img src="https://wallpapers.com/images/hd/cat-with-shades-cool-picture-lkenou4wsqrbib37.jpg" alt="Shoes" /></figure>
        <div class="card-body">
            <h2 class="card-title">
                Shoes!
                <div class="badge badge-secondary">NEW</div>
            </h2>
            <p>If a dog chews shoes whose shoes does he choose?</p>
            <div class="card-actions justify-end">
                <div class="badge badge-outline">Fashion</div> 
                <div class="badge badge-outline">Products</div>
            </div>
        </div>
    </div>



    <div class="card w-96 bg-base-100 shadow-xl">
        <div class="card-body">
          <h2 class="card-title">This is the card that we just made</h2>
          <p>{person.name} {person.age}</p>
          <div class="card-actions justify-end">
            <button class="btn btn-primary">Buy Now</button>
          </div>
        </div>
    </div>



</div>