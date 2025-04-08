<h1>PVIFA/PVIF計算器</h1>  
<label for="C">請輸入債券票面利息C</label><br>
<input type="number" id="C"><br>
<label for="YTM">請輸入到期殖利率YTM / R，以%為單位</label><br>
<input type="number" id="YTM"><br>
<label for="F">請輸入債權面額F</label><br>
<input type="number" id="F"><br>
<label for="T">請輸入剩餘期數T</label><br>
<input type="number" id="T"><br>
<label for="Times">請輸入複息頻率，一年兩次請輸入2，以此類推</label><br>
<input type="number" id="Times"><br>
<br>
<button onclick="cal()">計算PVIFA與PVIF</button>
<h3>PVIFA : <span id="PVIFAresult"></span></h3>
<h3>PVIF : <span id="PVIFresult"></span></h3>
<h3>PV : <span id="PVresult"></span></h3>
<script>
    function cal(){
        const c=parseFloat(document.getElementById("C").value);
        const ytm=parseFloat(document.getElementById("YTM").value);
        const f=parseFloat(document.getElementById("F").value);
        const t=parseFloat(document.getElementById("T").value);
        const times=parseFloat(document.getElementById("Times").value);

        if(!isNaN(c)&&!isNaN(ytm)&&!isNaN(f)&&!isNaN(t)&&!isNaN(times)){
            const pvifa=(1-(1+((ytm/times)/100))**-t)/((ytm/times)/100);
            const pvif=((1+((ytm/times)/100))**-t);
            const pv=c*pvifa+f*pvif;
            document.getElementById("PVIFAresult").textContent=pvifa;
            document.getElementById("PVIFresult").textContent=pvif;
            document.getElementById("PVresult").textContent=pv;
        }
        else{
            document.getElementById("PVIFAresult").textContent="請輸入有效的數字";
            document.getElementById("PVIFresult").textContent="請輸入有效的數字";
            document.getElementById("PVresult").textContent="請輸入有效的數字";

        }
    }
</script>
<style>
    button{
        color:aliceblue;
        background-color: black;
        border-radius: 30px;
        border-style: none;

    }
    button:hover{
        background-color: rgb(46, 46, 46);
    }
    button:active{
        background-color: rgb(126, 124, 124);
    }

</style>
