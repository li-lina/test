package basic;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

public class SeleniumFirstScript {
	
	public static void main(String[] args) {
	
	webdriver driver=new FirefoxDriver();
	driver.get("http://13.75.189.136:8081");
	driver.findElement(By.id("username")).sendKeys("ubiquity");
	driver.findElement(By.id("password")).sendKeys("P@ss123#UbiQuity");
	driver.findElement(By.type("submit")).click();
	
	String expected_title = "Ubiquity QA";
	String actual_title=driver.getTitle();
	if (expected_title.equals(actual_title))
	{
		System.out.println("Welcome to the Ubiquity Tester admin page.");
	}else {
		System.out.println("Incorrect username or password.");
	}
	
	driver.findElement(By.linkText("Edit Profile")).click();
	driver.findElement(By.id("Email")).sendKeys("111");
	driver.findElement(By.id("DateOfBirth")).sendKeys("111");
	driver.findElement(By.id("NewPassword")).sendKeys("111");
	driver.findElement(By.id("ConfirmNewPassword")).sendKeys("111");
	driver.findElement(By.xpath("[onclick='submitFunction()']")).click();
	
	String expected_alert = "SuccessMessage";
	String actual_alert=driver.getTitle();
	if (expected_title.equals(actual_alert))
	{
		System.out.println("Update is successful! Please see updated information below.");
	}else {
		System.out.println("Update Failed! The passwords don't match.");
	}	
	}
}
