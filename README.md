# Gmailtext
package web_driver;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class Verify_gmailtext {

	public static void main(String[] args) throws Throwable {
		// TODO Auto-generated method stub
		System.setProperty( "webdriver.chrome.driver","E:\\Chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		driver.manage().window().maximize();
		driver.manage().deleteAllCookies();
		driver.get("https://www.google.com/");
		Thread.sleep(5000);
		//capture gmail link from google page
		String Expected=driver.findElement(By.linkText("Gmail")).getText();
		//capture gmail link url
		String linkUrl=driver.findElement(By.linkText("Gmail")).getAttribute("href");
		System.out.println(linkUrl);
		String Actual="gmail";
		if(Expected.equalsIgnoreCase(Actual))
		{
			System.out.println("Link found in page::"+Expected+"  "+Actual);
		}
		else {
			System.out.println("Link not found in page::"+Expected+"  "+Actual);
		}
		driver.close();
				
		

	}

}
