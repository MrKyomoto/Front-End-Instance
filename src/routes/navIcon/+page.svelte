<script lang="ts">
    // let navIcons = document.querySelectorAll("nav-icon");

    //navIcons.forEach((navIcon)=>{navIcon.addEventListener("click", ()=>{this,classList.toggle("open")})});
    function Open(event:Event){
        event!.target.classList.toggle("open");
    }
</script>

<div class="container">
    <main>
        <div class="nav-icon" id="nav-icon-1" on:click ={Open} >
            <span style="--i: 0"></span>
            <span style="--i: 1"></span>
            <span style="--i: 2"></span>
        </div>

        <div class="nav-icon" id="nav-icon-2" on:click={Open}>
            <span style="--i: 0"></span>
            <span style="--i: 0"></span>
            <span style="--i: 1"></span>
            <span style="--i: 1"></span>
            <span style="--i: 2"></span>
            <span style="--i: 2"></span>
        </div>

        <div class="nav-icon" id="nav-icon-3" on:click={Open}>
            <span style="--i: 0"></span>
            <span style="--i: 1"></span>
            <span style="--i: 1"></span>
            <span style="--i: 2"></span>
        </div>



        <div class="nav-icon" id="nav-icon-4" on:click={Open}>
            <span style="--i: 0"></span>
            <span style="--i: 1"></span>
            <span style="--i: 2"></span>
        </div>
    </main>
</div>

<style>
    * {
        margin:0;
        padding:0;
        box-sizing:border-box;
    }

    .container{
        display: flex;
    }

    main{
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        background-color: white;
        padding-left: 10%;
    }

    /*汉堡菜单公共样式 */
    .nav-icon{
        position:relative;
        width:60px;
        height:45px;
        margin:50px;
        transform:rotate(0deg);
        -webkit-transition:0.5s ease-in-out;
        transition:0.5s ease-in-out;
        cursor:pointer;
    }

    .nav-icon span{
        display:block;
        position:absolute;
        left:0;
        height:9px;
        width: 100%;
        background-color: tomato;
        border-radius: 9px;
        opacity: 1;
        transform:rotate(0deg);
        transition:0.25s ease-in-out;
    }

    /* 样式一 */
    #nav-icon-1 span{
        top:calc(var(--i)*18px);
    }

    :global(#nav-icon-1.open) span:nth-child(1){
        top:18px;
        transform:rotate(135deg);
    }

    :global(#nav-icon-1.open) span:nth-child(2){
        opacity: 0;
        left:-60px;
    }

    :global(#nav-icon-1.open) span:nth-child(3){
        top:18px;
        transform: rotate(-135deg);
    }

    /* 样式二 */
    #nav-icon-2 span{
        left:unset;
        width:50%;
    }

    :global(#nav-icon-2) span:nth-child(even){
        left:50%;
        border-radius: 0 9px 9px 0;
    }

    :global(#nav-icon-2) span:nth-child(odd){
        left:0;
        border-radius: 9px 0 0 9px;
    }

    #nav-icon-2 span{
        top:calc(var(--i)*18px);
    }

    :global(#nav-icon-2.open) span{
        width:55%;
    }

    :global(#nav-icon-2.open) span:nth-child(1),:global(#nav-icon-2.open) span:nth-child(6){
        transform: rotate(45deg);
    }

    :global(#nav-icon-2.open) span:nth-child(2),:global(#nav-icon-2.open) span:nth-child(5){
        transform: rotate(-45deg);
    }

    :global(#nav-icon-2.open) span:nth-child(1){
        left:5px;
        top:7px;
    }
    :global(#nav-icon-2.open) span:nth-child(2){
        left:calc(50%-5px);
        top:7px;
    }
    :global(#nav-icon-2.open) span:nth-child(3){
        left:-50%;
        opacity: 0;
    }
    :global(#nav-icon-2.open) span:nth-child(4){
        left:100%;
        opacity: 0;
    }
    :global(#nav-icon-2.open) span:nth-child(5){
        left:5px;
        top: 29px;
    }
    :global(#nav-icon-2.open) span:nth-child(6){
        left:calc(50%-5px);
        top: 29px;
    }

    /* 样式三 */
    #nav-icon-3 span{
        top:calc(var(--i)*18px);
    }

    :global(#nav-icon-3.open) span:nth-child(1),
    :global(#nav-icon-3.open) span:nth-child(4){
        top:18px;
        width:0%;
        left:50%;
    }

    :global(#nav-icon-3.open) span:nth-child(2){
        transform: rotate(45deg);
    }
    :global(#nav-icon-3.open) span:nth-child(3){
        transform: rotate(-45deg);
    }

    /* 样式四 */
    #nav-icon-4 span{
        top:calc(var(--i)*18px);
        transform-origin: left center;
    }

    :global(#nav-icon-4.open) span:nth-child(1){
        transform: rotate(45deg);
        top:-3px;
        left: 8px;
    }

    :global(#nav-icon-4.open) span:nth-child(2){
        width: 0%;
        opacity: 0;
        left:-50%;
    }

    :global(#nav-icon-4.open) span:nth-child(3){
        transform: rotate(-45deg);
        top:39px;
        left:8px;
    }
</style>