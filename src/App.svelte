<script>
import './bootstrap.bundle.min.js';
import './w3.css';
import './bootstrap.min.css';


var aa = '';
var bb = '' ;
var cc = '';
var dd = '';
var width = '';
var widthT = '' ;
var length = '';
var weight = '';
var wastagep = '';
var wastagek = '';
var volume = '';
var degree = '';
var slant = "" ;

function weigh(){var sl = (bb - cc) * (bb - cc) + (aa*aa ) ; sl = Math.sqrt(sl); sl = sl.toFixed(2) ; slant = sl ;
                 var ra = bb/2 ; var rb = cc/2; var ha = aa*.0254 ; ra = ra*.0254 ; rb = rb * .0254 ; var ta = dd * .001 ;
                 var csa = 3.14 * ha*(ra+rb) ; csa = csa * ta ; csa = csa * 7930 ; weight = csa ; weight = weight.toFixed(3);
                 var ma = bb/2 ; var mb = cc/2 ;
                 var vv = 1.0466666667*aa*((ma*ma)+(mb*mb)+(ma*mb))*.0163871 ;
                 vv = vv.toFixed(0) ;
                 volume = vv ;
                 }

function tape(){var gfd = bb*3.14*.0254*1000 ; gfd = gfd.toFixed(2) ; var tey = cc*3.14*.0254*1000 ; tey = tey.toFixed(2) ;
                var khv = aa*.0254*1000 ; khv = khv.toFixed(2);
                degree = (gfd - tey )/khv ; degree = degree*.5 ; console.log(degree); degree = Math.atan(degree); console.log(degree); degree = degree*(180/3.14); degree = degree.toFixed(2);
              }

function blank(){var iii = aa*.0254 ; var jjj = bb*3.14*.0254 ; var uuu = dd*.001; var ppp = iii * jjj * uuu *7930 ; ppp = ppp.toFixed(3);
                var ra = bb/2 ; var rb = cc/2; var ha = aa*.0254 ; ra = ra*.0254 ; rb = rb * .0254 ; var ta = dd * .001 ;
                 var csa = 3.14 * ha*(ra+rb) ; csa = csa * ta ; csa = csa * 7930 ; csa = csa.toFixed(3) ; 
                 wastagek = ppp - csa ;
                 wastagep = 100*(wastagek/ppp) ; wastagep = wastagep.toFixed(2) ;
                     }

function final(){length = aa ; width =  bb * 3.14 ; width = width.toFixed(2);
                               widthT = cc * 3.14 ; widthT = widthT.toFixed(2) ;
                               weigh();
                               tape(); 
                               blank();
                               
                               }

</script>
<style>
.aaaa{
    display: flex;
    background-color: #001d3d;
    height: 70px;
    justify-content: center;
}
.bbbb{
    color: #ffc300;
    justify-self: center;
    align-self: center;
}
.cccc{
   height: 100px; 
}
.aa{
    display: flex;
    flex-direction: column;
    background-color: #003566;
    height: 620px;
}
.bb{
    height: 40%;
    background-color:#ffc300;
    display: flex;
    flex-direction: column;
    justify-content: center;
}
.cc{
    height: 50%;
    display: flex;
    flex-direction: column;
    justify-content: center;

}
.dd{
    display: flex;
    width: 100%;
    margin-top: 13px;
}
.xx{
    color: #ffc300;
    font-family: monospace;
    margin-top: 10px;
    margin-left:10px ;
    font-size: 1.2rem;
}
.aaa{
    display: flex;
    background-color: #001d3d;
    height: 70px;
    justify-content: center;
    justify-content: space-evenly;
}
.ccc{
    height: 50px;
    align-self: center;
}
.bbb{
    height: 100px;
}
.am{
  width: 30%;
  margin-left: 20px;
}
.zm{
  font-family: monospace;
  margin-left: 10px;
  font-size: 1.5rem;
  color: #001d3d;
}
.al{
    margin-top: 70px;
}
</style>
<div>
<div class="aaaa w3-top">
<h1 class="bbbb">Bucket App</h1>
</div>

<div class="cccc"></div>

<div class="aa">
  <div class="bb">
   <div class="dd"><h1 class="zm">Height (inch)&nbsp;&nbsp;&nbsp;: </h1><input type="number" class="form-control am" bind:value="{aa}"  /></div>
   <div class="dd"><h1 class="zm">Top-Dia (inch)&nbsp; : </h1><input type="number" class="form-control am"  bind:value="{bb}" /></div>
   <div class="dd"><h1 class="zm">Base-Dia (inch) : </h1><input type="number" class="form-control am" bind:value="{cc}"   /></div>
   <div class="dd"><h1 class="zm">Thickness (mm)&nbsp; : </h1><input type="number" class="form-control am" bind:value="{dd}"   /></div>
  </div> 
  <div class="cc">
   <h1 class="xx al">Length of Blank (req.) : {length} inch</h1>
   <h1 class="xx">Width of Blank  (req.) : {width} inch</h1>
   <h1 class="xx">Blank's Base Width   : {widthT} inch</h1>
   <h1 class="xx">Weight of Final Blank : {weight}  Kg</h1>
   <h1 class="xx">Slant Height of Bucket  : {slant} inch </h1>
   <h1 class="xx">Wastage (kg) : {wastagek} </h1>
   <h1 class="xx">Wastage (%) :  {wastagep} </h1>
   <h1 class="xx">Volume (ltr.) :  {volume} </h1>
   <h1 class="xx">Taper (degree) :  {degree} &#176; </h1>
  </div>
</div>

<div class="aaa w3-bottom">
<button class="btn btn-outline-warning ccc">Clear</button>
<button class="btn btn-outline-warning ccc" on:click="{final}">Calculate</button>
</div>

<div class="bbb"></div>


</div>
