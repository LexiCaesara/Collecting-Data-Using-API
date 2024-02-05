# Collecting-Data-Using-API
import pandas as pd
import json
import requests
api_url="http://127.0.0.1:5000/data"
def get_number_of_jobs_T(technology):
    number_of_jobs = 0
    payload = {"Key Skills": technology}
    r = requests.get(api_url, params=payload)
    if r.ok:
        data = r.json()
        number_of_jobs +=len(data)


    return technology,number_of_jobs
    get_number_of_jobs_T("Python")
    def get_number_of_jobs_L(location):
    
    number_of_jobs = 0
    payload = {"Location": location}
    r = requests.get(api_url, params=payload)
    if r.ok:
        data = r.json()
        number_of_jobs +=len(data)
    return location,number_of_jobs
    get_number_of_jobs_L("Los Angeles")
    loca = ['Los Angeles', 'New York', 'San Francisco', 'Washington DC', 'Seattle', 'Austin', 'Detroit']
loca
!pip3 install openpyxl
from openpyxl import Workbook
wb = Workbook()
ws = wb.active
ws
ws.append(['Location','Number_of_Jobs'])

for i in loca:
    ws.append(get_number_of_jobs_L(i))
    wb.save('job-postings.xlsx')
jobs_loca = pd.read_excel('job-postings.xlsx')
jobs_loca
languages = ['C', 'C#', 'C++','Java', 'JavaScript', 'Python', 'Scala', 'Oracle', 'SQL Server', 'MySQL Server', 'PostgreSQL', 'MongoDB']
languages
wb = Workbook()
ws= wb.active
ws
ws.append(['teachnology', 'number_of_jobs'])

for language in languages:
    ws.append(get_number_of_jobs_T(language))
    wb.save('job-language.xlsx')
jobs_lang = pd.read_excel('job-language.xlsx')
jobs_lang
