# AutoComplete01
It is a good AutoComplete exam 

import deneme.utilities.TestBase;
import org.junit.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;

import java.util.List;

public class D11_AutoComplete extends TestBase {

    @Test
    public void autoCompleteTest() {
        driver.get("https://jqueryui.com/autocomplete/");
        driver.switchTo().frame(0);
        WebElement inputBox = driver.findElement(By.id("tags"));
        inputBox.sendKeys("Apple");
//        ui-menu-item WILL ONLY BE AVAILABLE AFTER USER TYPE IN THE INPUT
//        TESTER SHOULD MAE A GOOD MANUAL TESTING TO GET OBSERVE THE BEHAVIOUR TO LOCATE THE ELEMENT
        WebElement succession = driver.findElement(By.className("ui-menu-item"));
//        succession.click(); //works
//        ALTERNATIVELY I can click with js
        clickByJS(succession);

    }

    @Test
    public void autoCompleteTest2() {
        driver.get("https://jqueryui.com/autocomplete/");
        driver.switchTo().frame(0);
        WebElement inputBox = driver.findElement(By.id("tags"));
        inputBox.sendKeys("A");
        List<WebElement> succession = driver.findElements(By.className("ui-menu-item"));

        for (WebElement each : succession) {
            System.out.println(each.getText());
            if (each.getText().equals("Java")) {
                each.click();
                break;
            }
        }

    }

}
