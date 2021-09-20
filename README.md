PUBLIC API https://csfiqhri.herokuapp.com/

https://github.com/fqhrmp/coba

https://cscoba.herokuapp.com/?person_age=3&person_income=3&person_home_ownership=OWN&person_emp_length=3&loan_intent=PERSONAL&loan_grade=C&loan_amnt=33&loan_int_rate=3&loan_percent_income=3&cb_person_default_on_file=Y&cb_person_cred_hist_length=3

API untuk akses dari web masih belum tersambung dengan model dan masih da error di file htmlnya, mungkin untuk contoh input bisa diakses melalui postman dbawah ini.

![image](https://user-images.githubusercontent.com/43493631/133956411-1462d047-cf80-4324-9baf-9c743bb6d0a4.png)


API POSTMAN https://csfiqhri.herokuapp.com/predict


Contoh input
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

Output
```
{
    "api_version": "v1",
    "model_version": "credit_risk_1.0.0",
    "result": "0.128"
}
```
![image](https://user-images.githubusercontent.com/43493631/133956366-8dcfead0-c9a8-498b-8446-5860905fc4c4.png)



