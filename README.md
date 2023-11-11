# Hospital-Api

localhost:8000/api/v1/doctors/register --POST:-

name: yournam
email:youremail
password:yourpassword

{
    "success": true,
    "body": {
        "_id": "654f65429c322b2a8097ba86",
        "name": "Revanth Reddy",
        "email": "revanth@gmail.com ",
        "password": "$2a$10$CtK/vUrD6dDopncoSOR3pezhiUqFxc8NxSSsNEQRb7CjHm9mGEt/6",
        "__v": 0
    },
    "msg": "Doctor Registered Sucessfully!"
}

LOGIN :

localhost:8000/api/v1/doctors/login --POST

email:your registred email
password: your password



{
    "success": true,
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY1NGY2NTQyOWMzMjJiMmE4MDk3YmE4NiIsImlhdCI6MTY5OTcwMjI4OCwiZXhwIjoxNjk5NzA5NDg4fQ.u8qTLhoN9jpLp2PRCLRmW8D1j5JaMqsNZ3gWAEAFn5Q",
    "msg": "Log In Sucessful! Keep the Token safe Revanth Reddy!"
}

Patients Registration:

localhost:8000/api/v1/patients/register  --POST

name:Patient name
phone: Ptient phone number

{
    "success": true,
    "body": {
        "reports": [],
        "_id": "654f68ca9c322b2a8097ba87",
        "name": "Ratient 1",
        "phone": "1234567",
        "__v": 0
    },
    "msg": "Patient Registered Sucessfully!"
}

Create a report:

localhost:8000/api/v1/patients/654f68ca9c322b2a8097ba87/create_report --POST

status: your status
date : today date


{
    "success": true,
    "body": {
        "_id": "654f6a0c9c322b2a8097ba88",
        "patient": "654f68ca9c322b2a8097ba87",
        "doctor": "654f65429c322b2a8097ba86",
        "status": "Negative",
        "date": "2023-11-11T11:48:28.121Z",
        "__v": 0
    },
    "msg": "Report Created Sucessfully!"
}

All Reports:


localhost:8000/api/v1/patients/654f68ca9c322b2a8097ba87/all_reports --GET

add authetication tocken in bearer 

{
    "success": true,
    "body": {
        "patient_name": "Ratient 1",
        "phone": "1234567",
        "reports": [
            {
                "doctor": "Revanth Reddy",
                "status": "Negative"
            }
        ]
    },
    "msg": "All reports of the patient!"
}

Fetch All Reports Based on a Status: 

localhost:8000/api/v1/reports/Negative --GET

{
    "success": true,
    "body": {
        "caseCount": 1,
        "report": [
            {
                "doctor": "Revanth Reddy",
                "patient": {
                    "name": "Ratient 1",
                    "phone": "1234567"
                }
            }
        ]
    },
    "msg": "All reports with the status!"
}
