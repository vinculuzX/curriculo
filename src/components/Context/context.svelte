<script>
    export let title="",
               title_info="",
               content_info="",
               textField="",     
               isAvatar = false , 
               isDescription = false;

    
</script>
<style>
    .container{
        display: grid;
        grid-column-gap: 10vw;
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
    }
</style>

<div class="container">
    <div class="title">
        {title}
    </div>
    <div class="container__info">
        <strong>{title_info} </strong> {content_info}
    </div>
    <div class="container_textField">
        {textField}
    </div>
    <div class="container-dotList">
        <ul>
            <li></li>
        </ul>
    </div>
    <div class="container-skillList">
        <ul>
            <li></li>
        </ul>
    </div>
</div>