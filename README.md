# sel1

from selenium import webdriver


# selenium 3
# driver=webdriver.Chrome(executable_path="C:\chrome driver\chromedriver.exe")
#
# driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login/")
#
# driver.find_element_by_name("txtUsername").send_keys("Admin")
# driver.find_element_by_ID("txtPassword").send_keys("admin@123")
# driver.find_element_by_ID("btnLogin").click()
#
# act_title=driver.title
# exp_title="OrangeHRM"
#
# if act_title==exp_title:
#     print("login test passed")
# else:
#     print("Login test failed")
#
# driver.close()

# selenium 4

from selenium.webdriver.chrome.service import Service
from selenium.webdriver.common.by import By

serv_obj=Service("C:\chrome driver\chromedriver.exe")

driver=webdriver.Chrome(service=serv_obj)

driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login/")

driver.find_element(By.NAME,"txtUsername").send_keys("Admin")

driver.find_element(By.ID, "txtPassword").send_keys("admin123")

driver.find_element(By.ID,"btnLogin").click()

act_title=driver.title
exp_title="OrangeHRM"

if act_title==exp_title:
    print("login test passed")

else:
    print("Login test failed")

driver.close()
