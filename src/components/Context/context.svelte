<script>
    export let title="",
               textField="",
               doList=[],
               dotSkill=[],
               infoList=[
                   {
                       type:"",
                       value:""
                   }
               ],
               hasInfo=false,
               hasDotSkill=false ,
               hasTextField = false,     
               hasDotList = false;


    
</script>
<style>
    .container{
        grid-template-columns: 2fr 6fr;
        grid-column-gap: 5vw;
        display: grid;
        margin: 60px 0px;
    }
    .title{
        font-family: Roboto;
        font-style: normal;
        font-weight: bold;
        font-size: 2rem;
        line-height: 37px;
        display: flex;
        align-items: center;
        text-align: right;
        text-transform: capitalize;
    }
    .block{
        font-family: Roboto;
        font-style: normal;
        font-weight: normal;
        font-size: 16px;
        line-height: 171%;
        max-width: 36vw;
    }

    .dotList > ul {
        list-style: disc;
    }
    .dotList > ul > li {
        margin: 12px 0px;
    }
</style>

<div class="container">
    <div class="title">
        { title }
    </div>
    {#if hasInfo}
    <div class="block container__info">
       <div class="block container_contact">
            <ul>
                {#each infoList as item}
                    <li><b>{item.type}</b><span>{item.value}</span></li>     
                {/each}
            </ul>
       </div>
    </div>
    {/if}
    {#if hasTextField}
        <div class="block container_textField">
            { textField }
        </div>
    {/if}
    {#if hasDotList}
        <div class="block dotList">
            <ul>
                {#each doList as item}
                    <li>{item}</li>
                {/each}
            </ul>
        </div>
    {/if}
<!--  
    <div class="container-skillList">
        <ul>
            <li></li>
        </ul>
    </div> -->
    <!--  
    <div class="container-experience">
        <ul>
            <li></li>
        </ul>
    </div> -->
</div>