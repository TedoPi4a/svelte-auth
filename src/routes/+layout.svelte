<script>
    import Myheader from './myheader.svelte';
    import './style.css'


</script>

<div>
    <div class="loader hidden">
        <img src="/Spinner1.gif" alt="">
    </div>
    <Myheader/>
    
    <main><slot/></main>

</div>

<style>
    main{
    }
    .loader{
        position: fixed;
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: #f1f2f3;
        z-index: 1;
    }
    .loader img{
        width: 6em;
    }
    .loader.hidden{
       animation:none .9s;
       animation-fill-mode: forwards;
    }
    @keyframes none{
        100% {
            visibility: hidden;
        }
    }
</style>