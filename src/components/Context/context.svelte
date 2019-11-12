<script>
    export let title="",
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
    <div class="topic__container">
        <strong>{titleTopic} : </strong> Rua do Sobe desce quer o numero desaparece, 313, Rio de Janeiro - RJ
    </div>
</div>