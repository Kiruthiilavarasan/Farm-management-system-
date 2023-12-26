<?php  
Session_start ();  require 
'../db.php';   
$sql = "SELECT * FROM blog data ORDER BY blogId DESC"; $result = mysqli_query ($conn, $sql);   while ($row = $result->fetch_array ()):   
?>   
<? = $row['likes']?>   
<?php endwhile?>   
. con {  border: 2px solid #dedede;  backgroundcolor: #f1f1f1;  borderradius: 5px;   padding: 10px;  margin: 10px 0;  color: #fff;  width: 650px;  height:80px;  wordwrap: break-word;   
}   
/* Darker chat container   
*/. darker {  border-color: #ccc; background-color: #000; float: right;  }   /* Clear floats */  . 
con::after {  content: "";   
clear: both;  display: table;   
}   
/* Style images */   
. con imp {  float: left;   
max-width: 60px;  width: 80%;  marginright: 20px; border-radius: 50%;}   
/* Style the right image */. con imp. right {            float: right;  margin-left: 20px;  margin-right:0;   
}   
/* Style time text  */. time-right {   
position: relative;  float: right;  color: #fff;   
}   
/* Style time text */   
. time-left {   
float: left;  color: #fff;   
}   
-- phpMyAdmin SQL Dump   
-- version 4.6.4   
-- https://www.phpmyadmin.net/ -
Host: 127.0.0.1   
-- Generation Time: Feb 26, 2018 at 07:52 AM -- Server version: 5.7.14   
-- PHP Version: 5.6.25  
SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";   
SET time zone = "+00:00";   
/*!40101 SET  
@OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;  
/*!40101   
  
  
SET  
@OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS  
*/; /*!40101 SET  
@OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION  
*/; /*!40101 SET NAMES utf8mb4 */;   
                MYSQL   
 Database: `agriculture`      
Table structure for table `blogdata`   
CREATE TABLE `blogdata` (   
`blogId` int (10) NOT NULL,   
`blog User` varchar (256) NOT NULL,   
`blog Title` varchar (256) NOT NULL,   
`blog Content` long text NOT NULL,   
`blog Time` timestamp NOT NULL DEFAULT  
CURRENT_TIMESTAMP, `likes` int (10) NOT NULL DEFAULT '0'   
) ENGINE=InnoDB DEFAULT CHARSET=latin1;   
 
Dumping data for table `blogdata`     
INSERT INTO `blogdata` (`blogId`, `blog User`, `blog Title`, `blog Content`, `blog Time`, `likes`) VALUES   
(19, 'The Phenom', 'First Blog', '<p>Its Awesome website<img alt="wink" src="https://cdn.ckeditor.com/4.8.0/full/plugins/smiley/images/wink_smile.png" style="height:23px; width:23px" title="wink" /></p>\r\n', '2018-02-25  
13:09:41', 1);   

 Table structure for table `blog feedback`      
CREATE TABLE `blog feedback` (   
`blogId` int (10) NOT NULL,   
`comment` varchar (256) NOT NULL,   
`comment User` varchar (256) NOT NULL,   
`commentPic` varchar (256) NOT NULL DEFAULT 'profile0.png',   
`comment Time` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP )  
ENGINE=InnoDB DEFAULT CHARSET=latin1;  
 
Dumping data for table `blogfeedback`   
   
INSERT INTO `blogfeedback` (`blogId`, `comment`, `comment User`, `commentPic`, 
`comment Time`) VALUES   
(19, 'Mast yarr', 'The Phenom', 'profile0.png', '2018-02-25   
13:09:54');  
Table structure for table `buyer`   
CREATE TABLE `buyer` (   
`bid` int (100) NOT NULL,   
`bname` varchar (100) NOT NULL,   
`busername` varchar (100) NOT NULL,   
`bpassword` varchar (100) NOT NULL,   
`bhash` varchar (100) NOT NULL,   
`bemail` varchar (100) NOT NULL,   
`bmobile` varchar (100) NOT NULL,   
`baddress` text NOT NULL,   
`bactive` int (100) NOT NULL DEFAULT '0' )  
ENGINE=InnoDB DEFAULT CHARSET=latin1;    
 Table structure for table `farmer`      
CREATE TABLE `farmer` (   
`fid` int (255) NOT NULL,   
`fname` varchar (255) NOT NULL,   
`fusername` varchar (255) NOT NULL,   
`fpassword` varchar (255) NOT NULL,   
`fhash` varchar (255) NOT NULL,   
`femail` varchar (255) NOT NULL,   
`fmobile` varchar (255) NOT NULL,   
`faddress` text NOT NULL,   
`factive` int (255) NOT NULL DEFAULT '0', `frating` int (11) NOT NULL DEFAULT  
'0', `picExt` varchar (255) NOT NULL DEFAULT 'png', `picStatus` int (10) NOT NULL  
DEFAULT '0’) ENGINE=InnoDB DEFAULT CHARSET=latin1;   
--   
-- Dumping data for table `farmer`  
--   
INSERT INTO `farmer` (`fid`, `fname`, `fusername`, `fpassword`, `fhash`, `femail`, 
`fmobile`, `faddress`, `factive`, `frating`, `picExt`, `picStatus`) VALUES   
(3, 'Kaivalya Hemant Mendki', 'The Phenom',   
'$2y$10$22ezmzHRa9c5ycHmVm5RpOnlT4LwFaDZar1XhmLRJQKGrcVRhPgti',  
'61b4a64be663682e8cb037d9719ad8cd', 'kmendki98@gmail.com', '8600611198', 'abcde',  
0, 0,   
'png', 0); 
Table structure for table `fproduct`   
CREATE TABLE `fproduct` (   
`fid` int (255) NOT NULL,   
`pid` int (255) NOT NULL,   
`product` varchar (255) NOT NULL,   
`pcat` varchar (255) NOT NULL,   
`pinfo` varchar (255) NOT NULL,   
`price` float NOT NULL,   
`pimage` varchar (255) NOT NULL DEFAULT 'blank.png',   
`picStatus` int (10) NOT NULL DEFAULT '0'   
) ENGINE=InnoDB DEFAULT CHARSET=latin1;  
  
 Dumping data for table `fproduct`    
INSERT INTO `fproduct` (`fid`, `pid`, `product`, `pcat`, `pinfo`, `price`, `pimage`, 
`picStatus`) VALUES   
(3, 27, 'Mango', 'Fruit', '<p>Mango raseela</p>\r\n', 500, 'Mango3.jpeg', 1), (3, 28,  
'Ladyfinger', 'Vegetable', '<p>Its veggie</p>\r\n', 1000, 'Ladyfinger3.jpg', 1), (3, 29, 'Bajra',  
'Grains', '<p>bajre di rti</p>\r\n', 400, 'Bajra3.jpg', 1),   
(3, 30, 'Banana', 'Fruit', '<p>Jalgaon banana</p>\r\n', 400,   
'Banana3.jpg', 1);   
                   Table structure for table `like data`   
CREATE TABLE `like data` (   
`blogId` int (10) NOT NULL,   
`blogUserId` int (10) NOT NULL   
) ENGINE=InnoDB DEFAULT CHARSET=latin1;    
 Dumping data for table `like data`   
INSERT INTO `like data` (`blogId`, `blogUserId`)
 VALUES   (19, 3);   
   
                   Table structure for table `my cart`   

BACK END   
           
           CREATE TABLE `my cart` (   
`bid` int (10) NOT NULL  
`pid` int (10) NOT NULL   
) ENGINE=InnoDB DEFAULT CHARSET=latin1;  
-- Dumping data for table `my cart`   
INSERT INTO `my cart` (`bid`, `pid`) VALUES (3, 27),   
(3, 30);  
   
Table structure for table `review`      
CREATE TABLE `review` (   
`pid` int (10) NOT NULL,   
`name` varchar (255) NOT NULL,   
`rating` int (10) NOT NULL,   
`comment` text NOT NULL   
) ENGINE=InnoDB DEFAULT CHARSET=latin1 
Table structure for table   
`transaction`    
CREATE TABLE `transaction` (   
`tid` int (10) NOT NULL, 
`bid` int (10) NOT NULL,  
`pid` int (10) NOT NULL,   
`name` varchar (255) NOT NULL,   
`city` varchar (255) NOT NULL,   
`mobile` varchar (255) NOT NULL,   
`email` varchar (255) NOT NULL,   
`pin code` varchar (255) NOT NULL,   
`addr` varchar (255) NOT NULL   
) ENGINE=InnoDB DEFAULT CHARSET=latin1;   
 
 Dumping data for table `transaction`   
INSERT INTO `transaction` (`tid`, `bid`, `pid`, `name`, `city`, `mobile`, `email`, `pincode`, 
`addr`) VALUES   
(1, 3, 28, 'sa, j, cns', 'sajc', 'sajch', 'kmendki98@gmail.com', 'sacu', 'ckaskjc');    
 Indexes for dumped tables   
  
                    input[type=text], input[type==password]   
{  
    width: 	100%;     padding: 12px 20px;     margin: 8px 0;  
    display: inline-block;     border: 1px solid #ccc;     box-sizing: border-box;    position: relative; }  
  
/* Set a style for all buttons */ button {  
    background-color: #4CAF50;      color: white;     padding: 14px 20px;     margin: 8px 0;     border: none;     cursor: pointer;     width: 60%;  
    position: relative;  
  
}  
            
             
              mycart.php  
  
<?php  
 session start ();  
require 'db.php';  
 if (! isset ($_SESSION ['logged in']) OR   $_SESSION ['logged in'] == 0)  
{  
                      $_SESSION['message'] = "You need to first login to access this page !!!";  
header ("Location: Login/error. Php");  
}  
       $bid = $_SESSION['id'];        if(isset($_GET['flag']))  
       {  
                      $pid = $_GET['pid'];  
                      $sql = "INSERT INTO my cart (bid, pid)  
                     VALUES ('$bid', '$pid')";  
                      $result = mysqli_query ($conn, $sql);  
      }  
  
?>  
<!DOCTYPE html>  
<html lang="end">  
               	<head>  
  	  	<meta charset="UTF-8">  
 	   	<title>Agriculture: My Cart</title>  
 <meta http-equiv="content-type content="text/html; charset=utf-8" />  
      <meta name="description" content="" />  
   	<meta name="keywords" content="" />    	<linkhref="bootstrap\CSS\bootstrap.min.css"  
                        rel="stylesheet">  
  	<script       src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script> <script src="bootstrap\js\bootstrap.min.js">  
           </script>  
             <! --[if lte IE 8]><script       src="CSS/ie/html5shiv.js"></script><! [endif]-->              <link rel="stylesheet" href="login.css"/>  
 	   	<script src="js/jquery.min.js"></script>  
 	   	<script src="js/skel.min.js"></script>  
 	   	<script src="js/skel-layers.min.js"></script>  
 	   	<script src="js/init.js"></script>  
 	   	<noscript>  	  	  	  
                     <link rel="stylesheet"                      
 href="CSS/skel.css" />  
         <link rel="stylesheet" href="CSS/style.css" />  
<link rel="stylesheet" href="CSS/style-xlarge.css" />  
       </noscript>  
   <! --[if lte IE 8]><link rel="stylesheet"       href="CSS/ie/v8.css" /> <! 
[endif]-->  
</head>  
 <body class>  
 	   	<?php  
require 	'menu. 	Php';  function data Filter($data) 
$data = trim($data);  
 	$data = stripslashes($data);  	  	  	  
$data = htmlspecialchars($data); return 
$data;  
}  
?>  
             <! -- One -->  
<section id="main" class="wrapper style1 align centre" >  
<div class="container">  
<h2>My Cart</h2>  
  
  <section id="two" class="wrapper style2 align      centre">  
<div class="container">  
<div class="row">  
<?php  
       $SQL = "SELECT * FROM my cart WHERE bid =     '$bid'";  
 $result = mysqli_query($conn, $sql); while 
($row = $result->fetch array ()):  
              $pid = $row['pid']  
              $sql = "SELECT * FROM fproduct WHERE pid =      '$pid'";  
    $result1 = mysqli_query ($conn, $SQL);  
     $row1 = $result1->fetch array ();  
    $picDestination="images/product Images/”. $row1['pimage'];  
             ?>  
<div class="col-md-4">  
<section>  
<strong>  
<h2 class="title" style="colour: black; ">  
<?php echo $row1['product'].'';?>  
</h2>  
</strong>  
<a href="review.php?pid=<?php echo  
 $row1['pid'] ;?>" >  
 <img class="image fit" src="<?php echo $picDestination;>" alt=" " />  
</a>  
             <div style="align: left">  
<blockquote>  
<?php echo "Type: “. $row1['pcat'].'';?>  
<br>  
<?php echo "Price: “. $row1['price'].' /-';?>  
<br>  
</blockquote>  
              </section>  
</div>  
  <?php endwhile; ?>  
               </div>  
               </section>  
</header>  
             </section>  
           </body>  
           </html>               
<?php   session_start ();  require 'db.php';             
         if ($_SERVER["REQUEST_METHOD"] ==  "POST")  
    {  
 $product Type = $_POST['type'];  
$ProductName = data Filter($_POST['pname']);  
$product Info = $_POST['pinfo'];  
$product Price = data Filter($_POST['price']);  
$fid = $_SESSION['id'];  
               $SQL = "INSERT INTO fproduct (fid, product, pcat, pinfo, price)  
            VALUES ('$fid', '$ProductName', '$productType','$productInfo','$product 
Price')";  
$result = mysqli_query ($conn, $SQL); if 
(! $result)  
{  
$_SESSION['message’] ="Unable to upload Product!!!";  header ("Location: Login/error. Php");  
} else 
{  
$_SESSION['message'] = "successful !!!"; }  
            $pic = $_FILES['productPic'];  
$picName = $pic['name'];  
$picTmpName = $pic['tmp_name'];  
$picSize = $pic['size'];  
$picError = $pic['error'];  
$picType = $pic['type'];  
$picExt = explode ('.', $picName);  
$picActualExt = strtolower(end($picExt));  
$allowed = array('jpg','jpeg','png');  
  
if (in_array ($picActualExt, $allowed))  
{ if ($picError === 
0)  {  
$_SESSION['productPicid’]=$_SESSION['id']; $picNameNew=$ProductName.  
 $SESSION['product Picid']. “.”.$picActualExt;  $SESSION['productPicName']=$picNameNe; $_SESSION['productPicExt'] 
= $picActualExt; $picDestination="images/productImages/".  
$picNameNew; move_uploaded_file($picTmpName, $picDestination);  
$id = $_SESSION['id'];  
  
$SQL = "UPDATE fproduct SET picStatus=1, pimage='$picNameNew' WHERE product='$ProductName';";  
  
$result = mysqli_query ($conn, $SQL); if($result)  
{  
  
$_SESSION['message'] = "Product Image Uploaded successfully !!!"; header 
("Location: market. Php");  
} else  
{  
//die("bad");  
$_SESSION['message'] = "There was an error in uploading your product, Image!  
Please Try again!"; header ("Location: 
Login/error. Php");  
} } else {  
$_SESSION['message'] = "There was an error in uploading your product image!  
Please Try again!"; header ("Location: 
Login/error. Php");  
} } else  
{  
$_SESSION['message'] = "You cannot upload files with this extension!!!"; header 
("Location: Login/error. Php");  
}  
}  
  
function data Filter($data)  
{  
$data = trim($data);  
$data = stripslashes($data); $data 
= htmlspecialchars($data); return 
$data;  
}  
?>  
Uploadproduct.php  
<!DOCTYPE html>  
<html lang="end">  
<head>  
<meta charset="UTF-8">  
<title>Agriculture</title>  
<meta http-equiv="content-type" content="text/html; charset=utf-8" />  
<meta name="description" content="" />  
<meta name="keywords" content="" />  
<link href="bootstrap\CSS\bootstrap.min.css" rel="stylesheet">  
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>  
<script src="bootstrap\js\bootstrap.min.js"></script>  
<! --[if lte IE 8]><script src="CSS/ie/html5shiv.js"></script><! [endif]-->  
<link rel="stylesheet" href="login.css"/>  
<link rel="stylesheet" type="text/CSS" href="indexFooter.css">  
<script src="js/jquery.min.js"></script>  
<script src="js/skel.min.js"></script>  
<script src="js/skel-layers.min.js"></script>  
<script src="js/init.js"></script>  
<no script>  
<link rel="stylesheet" href="CSS/skel.css" />  
<link rel="stylesheet" href="CSS/style.css" />  
<link rel="stylesheet" href="CSS/style-xlarge.css" />  
</no script>  
<script src="https://cdn.ckeditor.com/4.8.0/full/ckeditor.js"></script>  
<! --[if lte IE 8]><link rel="stylesheet" href="CSS/ie/v8.css" /><! [endif]-->  
</head>  
<body>  
  
<?php require 'menu. Php';?>  
  
<! -- One -->  
  
<section id="one" class="wrapper style1 align-centre">  
<div class="container">  
<form 	method="POST" 	action="uploadProduct.php" ectype="multipart/formdata">  
<h2>Enter the Product Information here...!!</h2>  
<br>  
<centre>  
<input type="file" name="productPic"></input>  
<br />  
</centre>  
<div class="row">  
<div class="col-sm-6">  
<div class="select-wrapper" style="width: auto" >  
<select name="type" id="type" required style="background-colour: white-collar: 
black;">  
<option value="" style="colour: black;">- Category -</option>  
<option value="Fruit" style="colour: black;">Fruit</option>  
<option value="Vegetable" style="colour: black;">Vegetable</option>  
<option value="Grains" style="colour: black;">Grains</option>  
</select>  
</div>  
</div>  
<div class="col-sm-6">  
<input type="text" name="pname" id="pname" value="" placeholder="Product  
Name" style="background-colour: white-collar: black;" />  
</div>  
</div>  
<br>  
<div>  
<text area name="pinfo" id="pinfo" rows="12"></textarea>  
</div>  
<br>  
<div class="row">  
<div class="col-sm-6">  
<input type="text" name="price" id="price" value="" placeholder="Price" style="background-colour: white-collar: black;" />  
</div>  
<div class="col-sm-6">  
<button class="button fit" style="width: auto; colour: black;">Submit</button>  
</div>  
</div>  
</form>  
</div>  
</section>  
  
<script>  
CKEDITOR.replace(‘pinfo’);  
</script>  
</body>  
</html>
