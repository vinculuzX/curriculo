<script>
    export let title="",
               textField="",
               doList=[],
               skillList=[
                   {
                       name:"",
                       percent:""
                   }
                ],
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

    import ProgressBar from '../Common/progress-bar.svelte'
    
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
        &__skillList{
            font-size: 16px;
            font-family: 'Roboto';
            .skill{
                 grid-template-columns: 24px 100px 250px 10px;
                 grid-column-gap: 25px;
                 display: grid;
                 align-items: baseline;
                 margin:10px 0px;
                 &__type{
                     text-transform: capitalize;
                     font-size: 18px;
                 }
                 &__level{
                    font-size:14px;
                    color:#767676
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
                    margin:11px 0px;
                    font-weight: bolder;
                }
                &__period{
                    width: 190px;
                    margin:9px 0px;
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
    .dot{
        width: 24px;
        height: 24px;
        background-color: #E8E8E8;
        border-radius: 50%;
        position: relative;
        top: 5px;
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
        text-transform: capitalize;
        text-align: right;
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
    <div class="container__skillList">
        {#each skillList as item}
            <div class="skill">
                <div class="dot"></div>
                <div class="skill__type">{item.name}</div>
                <div class="skill__progress">
                    <ProgressBar percent={item.percent}/>
                </div>
                <div class="skill__level">
                    {item.percent}%
                </div>
            </div>
        {/each}
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