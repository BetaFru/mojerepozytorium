# -*- coding: utf-8" -*
import unittest
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC


"""
Open page  wp.pl
Go to „poczta”
Login to user „testerwsb_t1”
Password „adam1234”
Check if there is a word „Odebrane”
Do the same with wrong password
Do the same with the wrong user
Do the same with wrong password and user

"""

valid_username = "testerwsb_t1"
valid_password = "adam1234"
wrong_username = "tetserwsb_t1"
wrong_password = "adam4321"

class WpPlSearch(unittest.TestCase):

    def setUp(self):
        self.driver = webdriver.Firefox()

    def test_mail(self):
        self.driver.get("http://www.wp.pl")
        self.driver.find_element_by_link_text('Poczta').click()
        login_field = WebDriverWait(self.driver, 10).until(
            EC.presence_of_element_located((By.ID, "login")))
        #login_field = self.driver.find_element_by_id("login")
        login_field.clear()
        login_field.send_keys(valid_username)
        password_field = self.driver.find_element_by_id("password")
        password_field.clear()
        password_field.send_keys(valid_password)
        self.driver.find_element_by_id("btnSubmit").click()
        odebrane = WebDriverWait(self.driver, 10).until(
            EC.presence_of_element_located((By.LINK_TEXT, 'Odebrane')))
        #odebrane.click()
        self.driver.find_element_by_link_text("wyloguj").click()

    def test_wrong_password(self):
        self.driver.get("http://www.wp.pl")
        self.driver.find_element_by_link_text('Poczta').click()
        login_field = WebDriverWait(self.driver, 10).until(
            EC.presence_of_element_located((By.ID, "login")))
        #login_field = self.driver.find_element_by_id("login")
        login_field.clear()
        login_field.send_keys(valid_username)
        password_field = self.driver.find_element_by_id("password")
        password_field.clear()
        password_field.send_keys(wrong_password)
        self.driver.find_element_by_id("btnSubmit").click()
        WebDriverWait(self.driver, 10).until(
            EC.presence_of_element_located((By.CLASS_NAME, "szary.error")))

    def test_wrong_user(self):
        self.driver.get("http://www.wp.pl")
        self.driver.find_element_by_link_text('Poczta').click()
        login_field = WebDriverWait(self.driver, 10).until(
            EC.presence_of_element_located((By.ID, "login")))
        #login_field = self.driver.find_element_by_id("login")
        login_field.clear()
        login_field.send_keys(wrong_username)
        password_field = self.driver.find_element_by_id("password")
        password_field.clear()
        password_field.send_keys(valid_password)
        self.driver.find_element_by_id("btnSubmit").click()
        WebDriverWait(self.driver, 10).until(
            EC.presence_of_element_located((By.CLASS_NAME, "szary.error")))

    def test_wrong_user_and_password(self):
        self.driver.get("http://www.wp.pl")
        self.driver.find_element_by_link_text('Poczta').click()
        login_field = WebDriverWait(self.driver, 10).until(
            EC.presence_of_element_located((By.ID, "login")))
        #login_field = self.driver.find_element_by_id("login")
        login_field.clear()
        login_field.send_keys(wrong_username)
        password_field = self.driver.find_element_by_id("password")
        password_field.clear()
        password_field.send_keys(wrong_password)
        self.driver.find_element_by_id("btnSubmit").click()
        WebDriverWait(self.driver, 10).until(
            EC.presence_of_element_located((By.CLASS_NAME, "szary.error")))

    def tearDown(self):
        self.driver.quit()


if __name__ == "__main__":
    unittest.main(verbosity=2)
