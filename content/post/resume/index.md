---
title: My Resume
description: If You Want To Know Me A Lot
slug: hydra-huo
date: 2022-10-18 00:00:00+0000
image: cover.jpg
categories:
    - Experience
tags:
    - Experience
---

## 

------

## **EDUCATION**

#### **Macau University of Science and Technology Business School**

***Bachelor of Business Administration in Marketing***

##### **Major Courses:** Management Mathematics, Microeconomics, Macroeconomics, Finance, Management Accounting, Financial Accounting, Marketing, Strategic Management, etc.

------

## **INTERNSHIPS**   

##### Baidu | Human Resources Intern | Beijing, China 

> Responsible for posting job vacancies, screening, and contacting candidates on Baidu's ERP intranet, Boss zhipin, Zhaopin, Liepin, and other online recruitment websites
>
>  Assisted in interviewing candidates: followed up the interview process; recorded and collated interview notes
>
>  Used Python to write a greeting program for Boss zhipin to automatically screen candidates who meet the job requirements and take the initiative to contact them to indicate the salary and job description
>
>  Recruited two E8 level candidates and seven E7 level candidates with a total of 21 people for Baidu's sales department

**Dana Times Technology Group Co., Ltd. | Intern of Marketing Department | Beijing, China**

> Analyze the keywords, clicks, visits, conversion rate, matching method and door-to-door rate of each SEM channel of Dana's adult education product line, and make a daily keyword report;
>
> Assist in the market research activities of "employment start-up" at the trainee meeting, and write the research and analysis report.
>
> Regularly collate all kinds of data reports by PowerBI, and assist the decision makers in the marketing department to grasp the market trends.
>
> Assist in planning the meeting activities of "100 Enterprises" large-scale employment college, export the activity planning scheme and participate in the implementation of the activity site.

------

## **ACADEMIC RESEARCH**  

**Non-pharmacological Interventions and Mass Screening for Infectious Diseases Outbreak COVID-19: Cost-effiectiveness Analysis**

>  Completed paper as a co-author, submitted to SCI
>
>  Cited journal and government website data as parameters for a Markov chain-based SEIR model
>
>  Employed treeage pro to simulate the one-year transmission of COVID-19 in Wuhan
>
> Conducted a cost-effectiveness analysis with the number of infections prevented, deaths, and incremental cost-effectiveness ratios (ICERs) as indicators

------

## **PROJECTS**

##### **Financial Investment Analysis Practical Training       **

> Chose ten stocks in different sectors to conduct portfolio analysis using Mean-Variance Analysis and Efficient Frontier
>
> Imported historical data downloaded from Yahoo Finance into excel to calculate functions to construct a full covariance matrix based on monthly returns
>
> Divided returns into 21 stocks based on Markowitz portfolio theory, calculated the corresponding minimum risk for each stock and plotted the risk-return
>

##### **KPMG Business Competition                    **

> Collected relevant data to assess the dynamics of ByteDance and attempted to give global strategy recommendations
>
> Listed ten strategic models in the strategic analysis phase, and applied SWOT, PEST, and Boston Matrix for analysis
>

------

## **STUDENT WORK**           

##### **Macau Social Practice Group | Head of Advertising Department **

> Responsible for writing promotional copy, leading the members to shoot and process videos and photos of various activities, with an average view of 4k+
>
> Designed posters, banners, exhibition boards, public website layouts, etc. 
>
> Regularly held software teaching classes on PS, AI, PR, AE, etc.

------

## **RELEVANT SKILLS**    

> Language ability: CET-4, CET-6, IELTS 6.5 Teaching in English during the undergraduate period
>
> Master: Windows Office, PS, AI, SAI, Procreate
>
> Know all about: Python,SQL,R language,PR,AE, Power BI, Markdown,E-prime
>
> Understand:LaTex,CSS language

------



------

This is the code I wrote while working at Baidu????

```python
from selenium import webdriver
from selenium.webdriver.common.action_chains import ActionChains
import random
import time

#???????????????
driver = webdriver.Chrome(r'D:\chromedriver.exe')
driver.maximize_window()
driver.implicitly_wait(5)
#????????????
login_link = 'https://login.zhipin.com/?ka=header-login'
driver.get(login_link)
time.sleep(8)
#????????????????????????
driver.find_element_by_class_name('icon-menu-recommend').click()
time.sleep(1)
#??????????????????????????????????????????????????????
def markElement(driver,element):
	driver.execute_script("arguments[0].setAttribute('style',arguments[1]);",element,"border:2px solid red;")
#??????????????????
def select(x):
    #d??????????????????
    dropdown = driver.find_element_by_xpath('/html/body/div[1]/div[1]/div/div/div[2]/div[2]/span')
    ActionChains(driver).click(dropdown).perform()
    #??????????????????
    selectxpath = '/html/body/div[1]/div[1]/div/div/div[2]/div[2]/div/ul/li['+str(x)+']'
    select = driver.find_element_by_xpath(selectxpath)
    global position
    position = select.text
    ActionChains(driver).click(select).perform()
    print("???????????????????????????"+position)
    time.sleep(1)
#?????????????????????????????????????????????
def load():
    i = 1
    while i < 15:
        driver.execute_script("var q=document.documentElement.scrollTop=10000")
        driver.execute_script('window.scrollBy(0,500)')
        time.sleep(1)
        print("?????????"+str(i)+"???")
        i += 1
#?????????(????????????50????????????????????????)
def greet():
    i = 2
    while i < 50:#???????????????1?????????2???????????????
        try:
            greetxpath = "/html/body/div/div/div/div/div[2]/div/div/div/div/ul/li["+str(i)+"]/div/div/div[2]/div/span/button"
            greetele = driver.find_element_by_xpath(greetxpath)
            greet = greetele.text
            agexpath = "/html/body/div/div/div/div/div[2]/div/div/div/div/ul/li["+str(i)+"]/div/div/div[3]/div[2]/div[2]/span[1]"
            ageele = driver.find_element_by_xpath(agexpath)
            agestr = ageele.text
            age = int(agestr[0:2])
            if 18 < age < 31 and greet != "????????????":
                markElement(driver,ageele)
                rt = random.randint(2,5)
                time.sleep(rt)#?????????????????????????????????????????????????????????????????????
                markElement(driver,greetele)
                ActionChains(driver).click(greetele).perform()#????????????????????????
                driver.execute_script('window.scrollBy(0,200)')
                print("???%d?????????,"%i,end="")
                print("??????%s."%agestr)
            else:
                print("???%d????????????,"%i,end="")
                print("??????%s."%agestr)
        except ValueError:
                print("???%d???????????????"%i)
        i += 1
#??????????????????
def task(y):
    select(y)
    driver.switch_to.frame("syncFrame")
    load()
    time.sleep(1)
    driver.execute_script("var q=document.documentElement.scrollTop=0")
    time.sleep(2)
    greet()
    time.sleep(2)
    driver.switch_to.default_content()
#?????????????????????
i = 2
while i < 8: #?????????6?????????
    if i == 4:
        i += 1
        continue
    task(i)
    print("??????--"+position+"--?????????")
    i += 1
```

