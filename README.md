# Robot.php
<?php

$xaxis=$argv[1];
$yaxis=$argv[2];
$d=(string)$argv[3];
$D= strtoupper($d);
$s=$argv[4];
$walknum="";

for($i=0;$i<strlen($s);$i++){
    if($s[$i]=="R"){
        $D=R($D);
      
    }
    else if($s[$i]=="L"){
        $D=L($D);
       
    }
    else if($s[$i]=="W"){
     
        $walknum=$s[$i+1];
       WN($walknum,$D);
       
    }
    
}

echo "op =$xaxis $yaxis $D";

function R($dir)
{
    
if($dir=="SOUTH"){
    
    return "EAST";
}
else if($dir=="WEST"){
    
    return "SOUTH";
}
else if($dir=="NORTH"){
    
    return "WEST";
}
else if ($dir=="EAST"){
    
    return "NORTH";
}
else{
    echo 'Enter valid direction';
}
    
}

function L($dir)
{
    echo "\n in L";
    if($dir=="SOUTH"){
    
        return "WEST";
}
else if($dir=="WEST"){
    
    return "NORTH";
}
else if($dir=="NORTH"){
    
    return "WEST";
}
else if ($dir=="EAST"){
    
    return "SOUTH";
}
else{
    echo 'Enter valid direction';
}

}

function WN($num,$dir){
   
    
    if($dir=="SOUTH"){
    $GLOBALS['yaxis']=$GLOBALS['yaxis']-$num;
    }
    else if($dir=="WEST")
    {
        $GLOBALS['xaxis']=$GLOBALS['xaxis']+$num;
    }
    else if($dir=="EAST"){
        $GLOBALS['xaxis']=$GLOBALS['xaxis']-$num;
    }
    else if($dir=="NORTH")
    {
        $GLOBALS['yaxis']=$GLOBALS['yaxis']+$num;
    }
   
}




