#Exercise Overview
- Risiko default kredit adalah risiko bahwa pemberi pinjaman mengambil kesempatan bahwa peminjam gagal melakukan pembayaran pinjaman yang diperlukan.

Dalam proyek ini, saya menggunakan algoritma pembelajaran  Logistic Regression untuk menemukan algoritma terbaik, dan di atas itu, saya juga menerapkan RandomizedSearchCV dan GridSearchCV untuk menyempurnakan hyperparamters dan lebih meningkatkan model .

Model akhir memiliki skor akurasi ROC-AUC TRAIN 0.8690897592668629
ROC-AUC TEST 0.87144598

# Observation
- person_income, person_emp_length, dan person_age: memiliki efek negatif pada loan_status menjadi default, yang berarti semakin besar variabel ini, semakin kecil kemungkinan orang tersebut berisiko.
loan_percent_income, loan_int_rate, dan loan_amnt: memiliki efek positif pada loan_status menjadi default, yang berarti semakin besar variabel ini, semakin besar kemungkinan orang tersebut berisiko.

# Handling Missing Value
- Hanya dua kolom data yang mempunyai missing value berisi NaN, 2 fitur yaitu 'person_emp_length' sebanyak 895 data (2,75% NaN) dan 'loan_int_rate' sebanyak 3116 (9,56% NaN)
- Kemudian fitur tersebut ditangani menggunakan nilai median dari masing-masing fitur

# Drop Data Duplicate
- Menghapus 165 baris duplikat

|Feature Name|	Description|	Value|
| --- | --- | --- |
|person_age	|Age.	|Integer|
|person_income	|Annual Income.|	Integer|
|person_home_ownership	|Home ownership.	|'RENT', 'MORTGAGE', 'OWN', or 'OTHER'|
|person_emp_length|	Employment length (in years)	|Integer|
|loan_intent	|Loan intent.|	'PERSONAL', 'EDUCATION', 'MEDICAL', 'VENTURE', 'HOMEIMPROVEMENT', or 'DEBTCONSOLIDATION'|
|loan_grade|	Loan grade.|	'A', 'B', 'C, 'D', 'E', 'F', or 'G'|
|loan_amnt|	Loan amount.|	Integer|
|loan_int_rate|	Interest rate.	|Float|
|loan_percent_income	|Percent income.|	Float|
|cb_person_default_on_file	|Historical default.|	'Y', or 'N'|
|cb_person_cred_hist_length	|Credit history length.	|Integer|

|Result|	Description|
| --- | --- |
|api_version	|The machine learning model.|
|model_version|	Model version.|
|result	|Probability estimates.|


- HTTP Method menggunakan POST dan GET


- PUBLIC API https://csfiqhri.herokuapp.com/

https://github.com/fqhrmp/coba

https://cscoba.herokuapp.com/?person_age=3&person_income=3&person_home_ownership=OWN&person_emp_length=3&loan_intent=PERSONAL&loan_grade=C&loan_amnt=33&loan_int_rate=3&loan_percent_income=3&cb_person_default_on_file=Y&cb_person_cred_hist_length=3

API untuk akses dari web masih belum tersambung dengan model dan masih da error di file htmlnya, mungkin untuk contoh input bisa diakses melalui postman dbawah ini.


API Heroku POSTMAN https://csfiqhri.herokuapp.com/predict
```
Request Header
```
![image](https://user-images.githubusercontent.com/43493631/133956411-1462d047-cf80-4324-9baf-9c743bb6d0a4.png)
```
```
![image](https://user-images.githubusercontent.com/43493631/133956534-7ae8e01b-2540-4b7f-8c25-bb47538d0277.png)
```
Output dari Terminal VSC
```
![image](https://user-images.githubusercontent.com/43493631/133956964-420f48da-defa-499a-8a3d-43e96a2aa3ec.png)
```
Output dari POSTMAN menggunakan GET http://127.0.0.1:3000/predict
```
![image](https://user-images.githubusercontent.com/43493631/133957132-535eaca6-fa1f-4463-94bf-117b7770d2e0.png)

Contoh input JSON untuk POSTMAN
```
{
    "person_age": 27,
    "person_income": 47900,
    "person_home_ownership": "OWN",
    "person_emp_length": 1,
    "loan_intent": "VENTURE",
    "loan_grade": "C",
    "loan_amnt": 7500,
    "loan_int_rate": 13.47,
    "loan_percent_income": 0.16,
    "cb_person_default_on_file": "N",
    "cb_person_cred_hist_length": 6
}
```

Output dari Heroku POSTMAN
```
{
    "api_version": "v1",
    "model_version": "credit_risk_1.0.0",
    "result": "0.128"
}
```

