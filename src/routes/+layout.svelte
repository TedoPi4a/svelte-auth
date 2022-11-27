<script>
    import Myheader from './myheader.svelte';
    import './style.css'
</script>

<div>
    <div class="loader"></div>
    <Myheader/>
    
    <main><slot/></main>
</div>

<style>
    main{
        margin: 0 auto;
        width: fit-content;
        margin-top: 12em;
    }
</style>