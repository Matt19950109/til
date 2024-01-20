### input.html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="UTF-8">
    <title>身長と体重を入力するページ</title>
    </head>
    <body>
    <h1>BMIを計算するプログラム</h1>
    <form action="bmicalc.jsp" method="post">
    	身長：<input type = "text" size="20" name="height1">
    	<br>
    	体重：<input type = "text" size="20" name="weight1">
    	<br>
    	<input type="submit" value="BMIを計算する">
    
    </form>
    
    </body>
    </html>

### bmicalc.jsp
        <%@ page language="java" contentType="text/html; charset=UTF-8"
            pageEncoding="UTF-8"%>
        <%
        	String value1 = request.getParameter("height1");
        	String value2 = request.getParameter("weight1");
        %>
        <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
        <html>
        <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <title>BMIの計算結果</title>
        </head>
        <body>
        <h1>あなたのBMIの計算結果</h1>
        
        <%
        	double height,weight;
        	height = Double.parseDouble(value1);
        	weight = Double.parseDouble(value2);
        	height /= 100;
        	
        	bmi = weight / (height * height);
        	
        	out.println("あなたのBMIの計算結果は"+ bmi + "です。");
        %>
        </body>
        </html>
