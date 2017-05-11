# mockfresher27
<%@page import="java.util.ArrayList"%>
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<%@ taglib uri="http://struts.apache.org/tags-bean" prefix="bean" %>
<%@ taglib uri="http://struts.apache.org/tags-html" prefix="html" %>
<%@ taglib uri="http://struts.apache.org/tags-logic" prefix="logic" %>
<%@ taglib uri="http://struts.apache.org/tags-tiles" prefix="tiles" %>
<!-- 
/**
 * AddRegion.jsp
 *
 * Date: May ‎8, ‎2017
 *
 * Copyright 
 *
 * Modification Logs:
 * DATE                 AUTHOR          DESCRIPTION
 * -----------------------------------------------------------------------
 * May ‎8, ‎2017        	VuNQ2         Create
 */
-->
<!DOCTYPE html>
<html>
<head lang="en">
<meta charset="UTF-8">
<title>AddRegion</title>
<link rel="stylesheet" href="css/bootstrap.min.css" />
<link rel="stylesheet" href="css/style.css" />
<script src="js/jquery-1.11.2.min.js"></script>
<script src="js/bootstrap.min.js"></script>
</head>
<script language="javascript" type="text/javascript">  

function replaceEnterCharacter() {
	 var des = $("#Box4").val().replace(/\n|\r/g, "br");
	$("#Box4").val(des); 
}

function SetFocus()  
{  
   document.getElementById('Box2').focus();  
   var x=document.getElementById('p1').innerHTML;
   var y=document.getElementById('p2').innerHTML;
   var z=document.getElementById('p3').innerHTML;
   x=x.replace(/\s/g,"");
   y=y.replace(/\s/g,"");
   z=z.replace(/\s/g,"");
   
   if(x!=""){
 	  document.getElementById('Box2').focus();  
 	    }
   else
   if(y!=""){
   document.getElementById('Box3').focus(); 
   }
   else
   if(z!="")
   {
	 	  document.getElementById('Box4').focus();  
	 	    }
}  
</script>
<body onload="SetFocus()">
	<div class="container">

		<br></br>
	       <div class="panel panel-primary"
			style="margin-bottom: 800px; width: 800px; margin-left: 150px">
			<div class="panel-heading">
				<h4>Add Region</h4>
			</div>
			
			<br>
			<html:form action="/themRegion" styleId="addStudent" method="post">
				<div class="row form-group">
					<label for="Region Code" class="col-lg-3" style="margin-left: 20px">Region
						Code<label style="color: red;">*</label><label>:</label>
					</label>
					<div class="col-lg-5">
						<html:text styleId="Box2" property="regionCode"
							styleClass="form-control" maxlength="" style="width:320px"></html:text>
						<p style="color: red" id="p1">
							<html:errors property="msvError" />
							<html:errors property="msvError2" />
							<html:errors property="msvError5" />
							<html:errors property="msvError6" />
							<html:errors property="RegionCodeError" />
						</p>
					</div>
				</div>
				<div class="row form-group">
					<label for="Region Name" class="col-lg-3" style="margin-left: 20px">Region
						Name<label style="color: red;">*</label><label>:</label>
					</label>
					<div class="col-lg-5">
						<html:text styleId="Box3" property="regionName"
							styleClass="form-control" maxlength="" style="width:320px"></html:text>
						<p style="color: red" id="p2">
							<html:errors property="msvError1" />
							<html:errors property="msvError3" />
							<html:errors property="msvError51" />
							<html:errors property="msvError61" />
						</p>
					</div>
				</div>
				<div class="row form-group">
					<label for="Description" class="col-lg-3" style="margin-left: 20px">Description:</label>
					<div class="col-lg-5">
						<html:textarea styleId="Box4" property="description"
							style="width:320px" rows="5" cols="50"></html:textarea>
						<p style="color: red" id="p3">
							<html:errors property="msvError4" />
						</p>
					</div>
				</div>
				<div class="row form-group" style="margin-left: 15px">
					<div class="col-lg-4 col-lg-offset-3">
						<button class="btn btn-primary" type="reset" style="width: 75px;">Clear</button>
						<input type="submit" class="btn btn-primary" name="submit"
							style="Width:75px" onclick="replaceEnterCharacter();" value="Add"/>
						<button class="btn btn-primary" onclick="history.go(-1);">Cancel</button>
					</div>
				</div>
			</html:form>
			</div>
			<br>
		</div>
	
</body>

</html>
