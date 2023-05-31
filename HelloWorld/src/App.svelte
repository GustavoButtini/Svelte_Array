<script>
  var B_Text = "Click to Insert";
  var Array_Show = "";
  var Inserted_Value = 0
  var Array_List = [];
  var Total_Positions = 0;
  var Is_Printed = false;

  function Inp_Cad(){
    if(Is_Printed == false){
      if(Total_Positions >= 0 && Total_Positions < 9){
        Array_List[Total_Positions] = Inserted_Value;
        Total_Positions++; 
        Array_Show = Array_Show + `  - ${Inserted_Value} -  `
      }else if(Total_Positions == 9){
        B_Text = "This is your last number, insert with caution";
        Array_List[Total_Positions] = Inserted_Value;
        Total_Positions++;
        Array_Show = Array_Show + `  - ${Inserted_Value} -  `
      }else if(Total_Positions == 10){
        B_Text = "Inserts blocked, max value inserted"
        Array_List[Total_Positions] = Inserted_Value;
        Total_Positions++;
        Is_Printed = true;
        Array_Show = String(Array_List);
      }
    }else{
      alert("Inserts Blocked, max value inserted")
    }
    
  }

</script>

<main>
  <div class="Head">
    <header class="Top_Header">
      <h1 class="Title_1 Title_Top_1">Welcome to my site</h1>
      <img class="Top_Logo" alt="Svelte Logo" width="100" height="100" src="https://cdn.icon-icons.com/icons2/2389/PNG/512/svelte_logo_icon_144827.png"/>
    </header>
  </div>
  <div class="Body">
    <h2 class="Header_2 Title_Top_1-5">On this site, you will can put an array of numbers and show them !</h2>
    <p class="Normal_Text Text_Superior_2 Flex_View">Insert here the numbers</p>
    <input class="Inserted_Value" bind:value={Inserted_Value} type="number"/><br>
    <button class="Button_1 Text_Superior_2" on:click={Inp_Cad}>{B_Text}</button>
    <p class="Normal_Text Text_Superior_2">The list will be shown here !</p><br>
    <p>{Array_Show}</p>
  </div>
</main>

<style>
  .Title_Top_1{
    font-size: clamp(20px 28px 32px);
    line-height: clamp(20px 28px 32px);
    font-weight: 700;
    font-family: "Arial";
    letter-spacing: 1px;
    color: #000;
  }
  .Title_Top_1-5{
    font-size: clamp(22px 30px 34px);
    line-height: clamp(22px 30px 34px);
    font-weight: 600;
    font-family: "Poppins";
    letter-spacing: 1px;
    color: #fff;
  }
  .Text_Superior_2{
    font-size: clamp(12px 16px 20px);
    line-height: clamp(12px 16px 20px);
    font-weight: 700;
    font-family: "Poppins";
    letter-spacing: 1px;
    color: #fff;
  }

  .Head{
    margin-bottom: 60px;
    background-image: url("/public/images.jpeg");
    background-size: cover;
    z-index: 2;
    width: 100%;
    background-color: rgba(0,0,0,0.6);
  }
  .Top_Header{
    height: 125px;
    width: 100% !important;
    display: flex;
    justify-content: space-between;
    position: sticky;
  }
  .Title_1{
    height: 200px;
    margin-left: 80px;
  }
  .Top_Logo{
    margin: 8.2px 40px 0 0;
  }


  .Body{
    height: 500px;
  }
  .Inserted_Value{
    background-color: rgb(0,0,0);
    color: #fff;
    margin-bottom: 20px;
  }
  .Flex_View{
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .Button_1{
    width: clamp(12.5vw 15vw 20vw);
    height: clamp(5vw 7.5vw 10vw);
    background-color: rgb(66, 0, 66);
    border-radius: 15px;
    transition: 0.3s;
    display: inline;
  }
  .Button_1:hover{
    width: clamp(15vw 20vw 225vw);
    height: clamp(7.5vw 10vw 12.5vw);
    background-color: rgb(0, 141, 0);
    border-radius: 15px;
    transition: 0.3s;
  }
</style>
