<script>
    export let title="",
               textField="",
               doList=[],
               dotSkill=[],
               expList=[
                   {
                    company:"",
                    start_date:"",
                    end_date:"",
                    description:"" 
                   }
               ],
               infoList=[
                   {
                       type:"",
                       value:""
                   }
               ],
               hasInfo=false,
               hasDotSkill=false ,
               hasTextField = false,     
               hasDotList = false,
               hasExperience = false;


    
</script>
<style lang="scss">
    .container{
        grid-template-columns: 2fr 6fr;
        grid-column-gap: 5vw;
        display: grid;
        margin: 60px 0px;
        &__contact{ 
            font-size: 16px;
            .contact{
            display: grid;
            grid-template-columns: 2fr 6fr;    
                &__type{
                    font-size: 16px;
                    font-weight: bold;
                    text-transform: capitalize;
                }
            } 
        }
        &__experience{
            font-size: 16px;
            font-family: 'Roboto';
            .job{
                display: grid;
                &__title{
                    text-transform: uppercase;
                    font-size: 22px;
                    margin:6px 0px;
                    font-weight: bolder;
                }
                &__period{
                    width: 190px;
                    margin:6px 0px;
                    font-weight: bold;
                    font-size:14px;
                    display: grid;
                    grid-template-columns: 2fr 5fr 2fr;
                }
                &__description{
                    font-size: 14px;
                    line-height: 29px;
                    margin:12px 0px;
                    width:45vw;
                    text-align: left;
                    color:#767676
                }

            }

        }    
    }
    .split-line{
        width:40px;
        height: 1px;
        background-color:#000;
        border-radius: 5px;
        margin:8px 12px;
    }
    .title{
        font-family: 'Roboto';
        font-style: normal;
        font-weight: bold;
        font-size: 2rem;
        line-height: 37px;
        display: flex;
        align-items: baseline;
        text-align: right;
        text-transform: capitalize;
    }
    .block{
        font-family: 'Roboto';
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
       <div class="block container__contact">
            {#each infoList as item}
                <div class="contact">
                    <div class="contact__type">{item.type}</div>
                    <div class="contact__value">{item.value}</div>   
                </div>
            {/each}
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
    {#if hasDotSkill}
    <div class="container-skillList">
        <ul>
            <li></li>
        </ul>
    </div>
    {/if}
    {#if hasExperience} 
    <div class="container__experience">
        {#each expList as item}
            <div class="job">
                <h4 class="job__title">{item.company}</h4>
                <div class="job__period">
                    {item.start_date}
                    <div class="split-line"></div>
                    {item.end_date}
                </div>
                <div class="job__description">
                    {item.description}
                </div>
            </div>
        {/each}
    </div>
    {/if}
</div>