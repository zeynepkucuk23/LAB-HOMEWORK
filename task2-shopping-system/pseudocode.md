START COURSE_REGISTRATION_SYSTEM
    DISPLAY "Welcome to Student Portal"
    INPUT student_credentials
    
    IF login_is_valid THEN
        START REGISTRATION_LOOP
            REPEAT
                DISPLAY "1. View Courses, 2. Register for Course, 3. View Schedule, 4. Logout"
                INPUT student_choice
                
                IF student_choice == 1 THEN
                    DISPLAY list_of_available_courses
                
                ELSE IF student_choice == 2 THEN
                    INPUT course_code
                    // Nested Conditions for Registration
                    IF course_exists THEN
                        IF NOT course_already_taken THEN
                            IF course_capacity > 0 THEN
                                REGISTER student
                                DISPLAY "Registration Successful"
                                course_capacity = course_capacity - 1
                            ELSE
                                DISPLAY "Error: Course is Full"
                            END IF
                        ELSE
                            DISPLAY "Error: Already Registered"
                        END IF
                    ELSE
                        DISPLAY "Error: Invalid Course Code"
                    END IF
                    
                ELSE IF student_choice == 3 THEN
                    DISPLAY current_student_schedule
                END IF
                
            UNTIL student_choice == 4
        END REGISTRATION_LOOP
    ELSE
        DISPLAY "Access Denied: Invalid Login"
    END IF
END COURSE_REGISTRATION_SYSTEM
