json_dynamic_form
=================

dynamic forms discused and implemented with Pravin Mishra @ m-sa for klinks.

JSON format would be :

{
    "form": {
        "id": 123456789,
        "name": "Applicationform",
        "season": 123456789,
        "panel": [
            {
                "name": "Childinformation",
                "field": [
                    {
                        "id": "lname",
                        "name": "Lastname",
                        "unique": "univ",
                        "required": "true",
                        "validation_message": "Last Name is Required !!!"
                    },
                    {
                        "id": "fname",
                        "name": "Firstname",
                        "unique": "univ",
                        "required": "true"
                    },
                    {
                        "id": "pname",
                        "name": "Preferredname/nickname",
                        "unique": "univ",
                        "required": "true"
                    },
                    {
                        "id": "sex",
                        "name": "Sex",
                        "unique": "univ",
                        "type": "select",
                        "selection_list": [
                            [
                                "",
                                ""
                            ],
                            [
                                "Male",
                                "Male"
                            ],
                            [
                                "Female",
                                "Female"
                            ]
                        ],
                        "lookup": "sex",
                        "required": "true"
                    },
                    {
                        "id": "birthdate",
                        "name": "Birthdate",
                        "unique": "univ",
                        "type": "date",
                        "required": "true"
                    },
                    {
                        "id": "food_allergies",
                        "name": "Foodallergies",
                        "unique": "univ",
                        "type": "textarea"
                    },
                    {
                        "id": "medical_issues'",
                        "name": "Medicalissues",
                        "unique": "univ",
                        "type": "textarea"
                    },
                    {
                        "id": "special_needs",
                        "name": "Specialneeds",
                        "unique": "univ",
                        "type": "textarea"
                    },
                    {
                        "id": "123456789_app_anything_else",
                        "name": "AnythingelseweatPeachtreePresbyterianshouldknowaboutthischild?",
                        "unique": "org",
                        "type": "textarea"
                    }
                ]
            },
            {
                "name": "Enrollment",
                "field": [
                    {
                        "id": "123456789_123456789_family_currently_enrolled",
                        "name": "Familycurrentlyenrolled?",
                        "unique": "seas",
                        "type": "select",
                        "lookup": "yesno",
                        "required": "true"
                    },
                    {
                        "id": "123456789_active_members_of_church",
                        "name": "ActivemembersofPeacthreePresbyterianChurch?",
                        "unique": "org",
                        "type": "select",
                        "lookup": "yesno",
                        "required": "true"
                    },
                    {
                        "id": "123456789_123456789_session",
                        "name": "Agegroupandschooldays",
                        "unique": "seas",
                        "type": "select",
                        "lookup": "123456789_session",
                        "required": "true"
                    }
                ]
            },
            {
                "name": "Parents",
                "fieldgroup": {
                    "multiply": "true",
                    "multiply_default": 2,
                    "multiply_link": "Addadditionalparents",
                    "field": [
                        {
                            "id": "parent_relationship",
                            "name": "Myrelationshiptotheapplicant",
                            "unique": "univ",
                            "type": "select",
                            "lookup": "relationship",
                            "required": "trueif",
                            "required_if": [
                                {
                                    "operator": "=",
                                    "expr": 1,
                                    "field_group_multiple_count": 0
                                },
                                {
                                    "parent_lname": "nonempty"
                                },
                                {
                                    "parent_fname": "nonempty"
                                },
                                {
                                    "parent_email": "nonempty"
                                },
                                {
                                    "parent_phone1": "nonempty"
                                },
                                {
                                    "parent_phone2": "nonempty"
                                },
                                {
                                    "parent_phone3": "nonempty"
                                }
                            ]
                        },
                        {
                            "id": "parent_lname",
                            "name": "Lastname",
                            "unique": "univ",
                            "required": "trueif",
                            "required_if": [
                                {
                                    "operator": "=",
                                    "expr": 1,
                                    "field_group_multiple_count": 0
                                },
                                {
                                    "parent_relationship": "nonempty"
                                },
                                {
                                    "parent_fname": "nonempty"
                                },
                                {
                                    "parent_email": "nonempty"
                                },
                                {
                                    "parent_phone1": "nonempty"
                                },
                                {
                                    "parent_phone2": "nonempty"
                                },
                                {
                                    "parent_phone3": "nonempty"
                                }
                            ]
                        },
                        {
                            "id": "parent_fname",
                            "name": "Firstname",
                            "unique": "univ",
                            "required": "trueif",
                            "required_if": [
                                {
                                    "operator": "=",
                                    "expr": 1,
                                    "field_group_multiple_count": 0
                                },
                                {
                                    "parent_relationship": "nonempty"
                                },
                                {
                                    "parent_lname": "nonempty"
                                },
                                {
                                    "parent_email": "nonempty"
                                },
                                {
                                    "parent_phone1": "nonempty"
                                },
                                {
                                    "parent_phone2": "nonempty"
                                },
                                {
                                    "parent_phone3": "nonempty"
                                }
                            ]
                        },
                        {
                            "id": "parent_email",
                            "name": "E-mailaddress",
                            "unique": "univ",
                            "required": "trueif",
                            "required_if": [
                                {
                                    "operator": "=",
                                    "expr": 1,
                                    "field_group_multiple_count": 0
                                },
                                {
                                    "parent_relationship": "nonempty"
                                },
                                {
                                    "parent_lname": "nonempty"
                                },
                                {
                                    "parent_fname": "nonempty"
                                },
                                {
                                    "parent_phone1": "nonempty"
                                },
                                {
                                    "parent_phone2": "nonempty"
                                },
                                {
                                    "parent_phone3": "nonempty"
                                }
                            ]
                        },
                        {
                            "id": "parent_phone1",
                            "name": "Phone#1",
                            "unique": "univ",
                            "type": "phone",
                            "required": "trueif",
                            "required_if": [
                                {
                                    "operator": "=",
                                    "expr": 1,
                                    "field_group_multiple_count": 0
                                },
                                {
                                    "parent_relationship": "nonempty"
                                },
                                {
                                    "parent_lname": "nonempty"
                                },
                                {
                                    "parent_fname": "nonempty"
                                },
                                {
                                    "parent_email": "nonempty"
                                },
                                {
                                    "parent_phone2": "nonempty"
                                },
                                {
                                    "parent_phone3": "nonempty"
                                }
                            ]
                        },
                        {
                            "id": "parent_phone2",
                            "name": "Phone#2",
                            "unique": "univ",
                            "type": "phone",
                            "required": "trueif",
                            "required_if": [
                                {
                                    "parent_relationship": "nonempty"
                                },
                                {
                                    "parent_lname": "nonempty"
                                },
                                {
                                    "parent_fname": "nonempty"
                                },
                                {
                                    "parent_email": "nonempty"
                                },
                                {
                                    "parent_phone1": "nonempty"
                                },
                                {
                                    "parent_phone3": "nonempty"
                                }
                            ]
                        },
                        {
                            "id": "parent_phone3",
                            "name": "Phone#3",
                            "unique": "univ",
                            "type": "phone",
                            "required": "trueif",
                            "required_if": [
                                {
                                    "parent_relationship": "nonempty"
                                },
                                {
                                    "parent_lname": "nonempty"
                                },
                                {
                                    "parent_fname": "nonempty"
                                },
                                {
                                    "parent_email": "nonempty"
                                },
                                {
                                    "parent_phone1": "nonempty"
                                },
                                {
                                    "parent_phone2": "nonempty"
                                }
                            ]
                        }
                    ]
                }
            }
        ]
    }
}