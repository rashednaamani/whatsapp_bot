import time
from selenium import webdriver
from selenium.webdriver.common.keys import Keys

contact_name_list = ['Myname']

text_ad = "YOUR WHATSAPP TEXT GOES HERE"

##................getting driver and web page......................................


def make_base():
    try:

        driver = webdriver.Firefox()
        driver.get("https://web.whatsapp.com/")
        time.sleep(30)
        return driver
    except:
        print "base problem"


##................. finding the contact and sending the text and image.............


def find_send(web_driver, contact_name):
    try:
        driver = web_driver
        contact = contact_name
        search_element = driver.find_element_by_class_name("input-search")
        search_element.clear()
        search_element.send_keys(contact)
        search_element.send_keys(Keys.ENTER)
        chat_body_ele = driver.find_elements_by_class_name("ellipsify")
        for c_b_e in chat_body_ele:
            check_cbe = contact in c_b_e.get_attribute("title")
            if check_cbe:
                c_b_e.click()
                input_elements = driver.find_elements_by_class_name("input")
                text_element = input_elements[1]
                text_element.send_keys(text_ad)
                text_element.send_keys(Keys.ENTER)
                text_element.clear()
                break
    except:
        print "some problem"
        #return


def main():

    web_driver = make_base()
    #while True:
    count = 0
    while count < len(contact_name_list):
          contact_name = contact_name_list[count]
          find_send(web_driver, contact_name)
          count += 1
    time.sleep(12000)
    web_driver.close()


if __name__ == '__main__':
    main()
