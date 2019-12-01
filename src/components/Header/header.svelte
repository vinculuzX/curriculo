<script>
    export let src = "https://miro.medium.com/max/1000/1*RbmhRUicKhfne7t_7Dqb5w.png",
               name = "Abraão",
               surname="Reis",
               ocupation="Front End Developer"; 

    const addIcons = '../../assets/images/add.png';
</script>
<style>
    .grid{
        display: grid
    }
    .header{
        grid-template-columns: 2fr 6fr;
        grid-column-gap: 5vw;
    }
    img{
        width: 189px;
        height: 189px;
        object-fit: cover;
        border-radius: 50%; 
    }
    p{
        font-family: Roboto;
        font-style: normal;
        font-weight: 500;
        font-size: 24px;
        line-height: 28px;
    }
    h1{
        margin:24px 0px;
        font-family: Roboto;
        font-style: normal;
        font-weight: bold;
        font-size: 56px;
        line-height: 66px;
    }
    h3{
        font-family: Roboto;
        font-style: normal;
        font-weight: 500;
        font-size: 32px;
        line-height: 37px;
    }
</style>

<div class="grid header">
    <div class="image-profile">
        <img src={src} alt="avatar">
        <img src={addIcons} alt="addIcons">
    </div>
    <div class="profile">
        <p>Olá , meu nome é</p>
        <h1>{name} • {surname}</h1>
        <h3>{ocupation}</h3>
    </div>
</div>