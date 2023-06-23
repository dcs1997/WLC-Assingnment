# WLC-Assingnment




<?php
// Your code here!
/* 

Burgerking sells three items: 
VegBurger which needs 2 breads & 1 veg pattice
NonVegBurger which needs 2 breads & 1 non-veg pattice
TikkiBurger which needs 2 breads & 1 tikki pattice

Given bread quantity, veg pattice quantity, non-veg pattice quantity, tikki pattice quantity & price of all 3 items

Print the total maximum possible profit by making all possible items based on bread availability 

Also, test for all inputs, we would change all the values while testing, the quantity values as well as price

And program has to be optimal with respect to time & space complexity

*/

$breads = 15;
$vegPattice = 3;
$nonVegPattice = 2;
$TikkiPattice = 1;
$priceVegBurger = 100;
$priceNonVegBurger = 125;
$priceTikkiBurger = 112;

$maxProfit = 0;

$maxBurger=floor($breads/2);

$maxCost=max($priceVegBurger, $priceNonVegBurger, $priceTikkiBurger);


$minCost=min($priceVegBurger, $priceNonVegBurger, $priceTikkiBurger);


for($i=0; $i<$maxBurger; $i++){
   
    if($maxCost==$priceNonVegBurger && $nonVegPattice>0){
       
        $maxProfit+=$priceNonVegBurger;
        $nonVegPattice--;
        
      }
      else  if($maxCost==$priceVegBurger && $vegPattice>0){
       
        $maxProfit+=$priceVegBurger;
        $vegPattice--;
       
        }
    
    else if($maxCost==$priceTikkiBurger && $TikkiPattice>0){
        $maxProfit+=$priceTikkiBurger;
      $TikkiPattice--;
       
        
    }
    
    
   else  if($maxCost!=$priceNonVegBurger && $minCost!=$priceNonVegBurger && $nonVegPattice>0){
        $maxProfit+=$priceNonVegBurger;
        $nonVegPattice--;
       
        
    }
    else  if($maxCost!=$priceVegBurger && $minCost!=$priceVegBurger && $vegPattice>0){
        $maxProfit+=$priceVegBurger;
        $vegPattice--;
       
        
    }
    
     else if($maxCost!=$priceTikkiBurger && $minCost!=$priceTikkiBurger && $TikkiPattice>0){
        $maxProfit+=$priceTikkiBurger;
      $TikkiPattice--;
      
       
        
    }
    
    
    
    
    else if($minCost==$priceNonVegBurger && $nonVegPattice>0){
        $maxProfit+=$priceNonVegBurger;
        $nonVegPattice--;
       
        
    }
    else  if($minCost==$priceVegBurger && $vegPattice>0){
        $maxProfit+=$priceVegBurger;
        $vegPattice--;
       
        
    }
    
    else if($minCost==$priceTikkiBurger && $TikkiPattice>0){
        $maxProfit+=$priceTikkiBurger;
        $TikkiPattice--;
       
        
    }
    
}



echo $maxProfit;






?>


