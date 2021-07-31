Selenium
========

准备：需要webdrive，比如chorme driver（需要把浏览器驱动放入系统路径中，或者直接告知selenuim的驱动路径）

**功能**

**元素定位/元素操作：**

find_element_by_id()

find_element_by_name()

find_element_by_class_name()

find_element_by_tag_name()

find_element_by_link_text()

find_element_by_partial_link_text()

find_element_by_xpath()

find_element_by_css_selector()

窗口大小：driver.set_window_size(480, 800)

后退/前进：

driver.back()

driver.forward()

刷新：driver.refresh()

点击和输入：

driver.find_element_by_id("kw").clear() 

driver.find_element_by_id("kw").send_keys("selenium") 

driver.find_element_by_id("su").click()

搜索框回车操作：

search_text = driver.find_element_by_id('kw') search_text.send_keys('selenium') search_text.submit()

size： 返回元素的尺寸。

text： 获取元素的文本。

get_attribute(name)： 获得属性值。

is_displayed()： 设置该元素是否用户可见。

**鼠标操作**：
在 WebDriver 中， 将这些关于鼠标操作的方法封装在 ActionChains 类提供。

perform()： 执行所有 ActionChains 中存储的行为；

context_click()： 右击；

double_click()： 双击；

drag_and_drop()： 拖动；

move_to_element()： 鼠标悬停

例：
above = driver.find_element_by_link_text("设置")

# 对定位到的元素执行鼠标悬停操作

ActionChains(driver).move_to_element(above).perform()

**键盘事件**

send_keys(Keys.BACK_SPACE) 删除键（BackSpace）

send_keys(Keys.SPACE) 空格键(Space)

send_keys(Keys.TAB) 制表键(Tab)

send_keys(Keys.ESCAPE) 回退键（Esc）

send_keys(Keys.ENTER) 回车键（Enter）

send_keys(Keys.CONTROL,'a') 全选（Ctrl+A）

send_keys(Keys.CONTROL,'c') 复制（Ctrl+C）

send_keys(Keys.CONTROL,'x') 剪切（Ctrl+X）

send_keys(Keys.CONTROL,'v') 粘贴（Ctrl+V）

send_keys(Keys.F1) 键盘 F1
……
send_keys(Keys.F12) 键盘 F12

**获取信息**

title = driver.title # 打印当前页面title

now_url = driver.current_url # 打印当前页面URL

user = driver.find_element_by_class_name('nums').text # # 获取结果数目

**等待页面加载完成**

**显式等待**使WebdDriver等待某个条件成立时继续执行，否则在达到最大时长时抛出超时异常：

element = WebDriverWait(driver, 5, 0.5).until(
                      EC.presence_of_element_located((By.ID, "kw"))
                      )
element.send_keys('selenium')
driver.quit()

**隐式等待**是告诉WebDriver去等待一定的时间后去查找元素。 默认等待时间是0秒

driver.implicitly_wait(10) # seconds 

**在不同的窗口和框架之间移动**

driver.switch_to_window("windowName")

driver.switch_to_frame("frameName")

直接取表单的id 或name属性。如果iframe没有可用的id和name属性，则可以通过下面的方式进行定位。

#先通过xpth定位到iframe

xf = driver.find_element_by_xpath('//*[@id="x-URS-iframe"]')

#再将定位对象传给switch_to_frame()方法

driver.switch_to_frame(xf)

完成了frame中的工作，我们可以这样返回父frame:

driver.switch_to_default_content()

**警告框处理**

alert = driver.switch_to_alert().action()

**cookie操作**
WebDriver操作cookie的方法：

get_cookies()： 获得所有cookie信息。

get_cookie(name)： 返回字典的key为“name”的cookie信息。

add_cookie(cookie_dict) ： 添加cookie。“cookie_dict”指字典对象，必须有name 和value 值。

delete_cookie(name,optionsString)：删除cookie信息。“name”是要删除的cookie的名称，“optionsString”是该cookie的选项，目前支持的选项包括“路径”，“域”。

delete_all_cookies()： 删除所有cookie信息

**调用JavaScript代码**

js="window.scrollTo(100,450);"

driver.execute_script(js) # 通过javascript设置浏览器窗口的滚动条位置

通过execute_script()方法执行JavaScripts代码来移动滚动条的位置。

Python+selenium使用cookie登录淘宝：
https://www.jianshu.com/p/773c58406bdb



































