# Homework_PY1511

1. Тест-кейс: Вход в систему с аккаунтом стандартного пользователя:

- Шаги:
1. Перейти на веб-сайт [Swag Labs](https://www.saucedemo.com).
2. Ввести "standard_user" в качестве имени пользователя.
3. Ввести действующий пароль.
4. Нажать кнопку "Войти".

- Ожидаемый результат: Пользователь должен успешно войти в систему.

2. Тест-кейс: Вход в систему с заблокированным пользовательским аккаунтом:

- Шаги:
1. Перейти на веб-сайт [Swag Labs](https://www.saucedemo.com).
2. Ввести "locked_out_user" в качестве имени пользователя.
3. Ввести действующий пароль.
4. Нажать кнопку "Войти".

- Ожидаемый результат: Пользователь должен получить сообщение об ошибке, указывающее на блокировку аккаунта.

3. Тест-кейс: Вход в систему с пользовательским аккаунтом с проблемами:

- Шаги:
1. Перейти на веб-сайт [Swag Labs](https://www.saucedemo.com).
2. Ввести "problem_user" в качестве имени пользователя.
3. Ввести действующий пароль.
4. Нажать кнопку "Войти".

- Ожидаемый результат: Пользователь должен успешно войти в систему.

4. Тест-кейс: Вход в систему с пользовательским аккаунтом, связанным с глюками производительности:

- Шаги:
1. Перейти на веб-сайт [Swag Labs](https://www.saucedemo.com).
2. Ввести "performance_glitch_user" в качестве имени пользователя.
3. Ввести действующий пароль.
4. Нажать кнопку "Войти".

- Ожидаемый результат: Пользователь должен смочь войти в систему, однако в процессе входа могут возникнуть проблемы с производительностью.

5. Тест-кейс: Вход в систему с пользовательским аккаунтом, связанным с ошибками:

- Шаги:
1. Перейти на веб-сайт [Swag Labs](https://www.saucedemo.com).
2. Ввести "error_user" в качестве имени пользователя.
3. Ввести действующий пароль.
4. Нажать кнопку "Войти".

- Ожидаемый результат: Пользователь должен получить сообщение об ошибке, указывающее на проблемы в процессе входа.

6. Тест-кейс: Вход в систему с пользовательским аккаунтом, связанным с визуальными проблемами:

- Шаги:
1. Перейти на веб-сайт https://www.saucedemo.com.
2. Ввести "visual_user" в качестве имени пользователя.
3. Ввести действующий пароль.
4. Нажать кнопку "Войти".

- Ожидаемый результат: Пользователь должен успешно войти в систему.

- Автотесты:

  from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

# driver = webdriver.Chrome()
# driver.maximize_window()
# driver.get("https://www.saucedemo.com")
# elem = driver.find_element(By.NAME,"user-name")
# elem.click()
# elem.send_keys("standard_user")
# elem = driver.find_element(By.NAME,"password")
# elem.clear()
# elem.send_keys("secret_sauce")
# elem.send_keys(Keys.ENTER)

# driver = webdriver.Chrome()
# driver.maximize_window()
# driver.get("https://www.saucedemo.com")
# elem = driver.find_element(By.NAME,"user-name")
# elem.click()
# elem.send_keys("locked_out_user")
# elem = driver.find_element(By.NAME,"password")
# elem.clear()
# elem.send_keys("secret_sauce")
# elem.send_keys(Keys.ENTER)

# driver = webdriver.Chrome()
# driver.maximize_window()
# driver.get("https://www.saucedemo.com")
# elem = driver.find_element(By.NAME,"user-name")
# elem.click()
# elem.send_keys("problem_user")
# elem = driver.find_element(By.NAME,"password")
# elem.clear()
# elem.send_keys("secret_sauce")
# elem.send_keys(Keys.ENTER)

# driver = webdriver.Chrome()
# driver.maximize_window()
# driver.get("https://www.saucedemo.com")
# elem = driver.find_element(By.NAME,"user-name")
# elem.click()
# elem.send_keys("performance_glitch_user")
# elem = driver.find_element(By.NAME,"password")
# elem.clear()
# elem.send_keys("secret_sauce")
# elem.send_keys(Keys.ENTER)

# driver = webdriver.Chrome()
# driver.maximize_window()
# driver.get("https://www.saucedemo.com")
# elem = driver.find_element(By.NAME,"user-name")
# elem.click()
# elem.send_keys("error_user")
# elem = driver.find_element(By.NAME,"password")
# elem.clear()
# elem.send_keys("secret_sauce")
# elem.send_keys(Keys.ENTER)

# driver = webdriver.Chrome()
# driver.maximize_window()
# driver.get("https://www.saucedemo.com")
# elem = driver.find_element(By.NAME,"user-name")
# elem.click()
# elem.send_keys("visual_user")
# elem = driver.find_element(By.NAME,"password")
# elem.clear()
# elem.send_keys("secret_sauce")
# elem.send_keys(Keys.ENTER)

import unittest
from selenium import webdriver
import time
import random
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
-------------------------------------------------------
class Logtest(unittest.TestCase):

    def setUp(self):
        self.driver = webdriver.Chrome()
        self.driver.get("https://www.saucedemo.com")
        self.driver.maximize_window()

    def tearDown(self):
        self.driver.quit()

    def test_login(self):
        usernames = ['standard_user', 'locked_out_user', 'problem_user', 'performance_glitch_user', 'error_user',
                     'visual_user']

        for username in usernames:
            username_field = self.driver.find_element(By.ID, 'user-name')
            username_field.clear()
            username_field.send_keys(username)
            password_field = self.driver.find_element(By.ID, 'password')
            password_field.clear()
            password_field.send_keys('secret_sauce')
            login_button = self.driver.find_element(By.ID, 'login-button')
            login_button.click()
            try:
                WebDriverWait(self.driver, 5).until(EC.url_contains('inventory.html'))
                print(f"Login successful with username: {username}")
            except:
                print(f"Login failed for username: {username}")
            menu_button = self.driver.find_element(By.ID, 'react-burger-menu-btn')
            menu_button.click()
            logout_link = self.driver.find_element(By.ID, 'logout_sidebar_link')
            logout_link.click()
