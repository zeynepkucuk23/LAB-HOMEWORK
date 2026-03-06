START
  DISPLAY "Welcome to the Course Registration System"
  INPUT "Enter Student ID and Password"
  
  IF login credentials are valid:
    DISPLAY "Available Courses: CS101, MATH201, ENG102"
    INPUT "Enter the Course Code you want to register"
    
    IF course exists AND quota > 0:
      ADD course to student's academic record
      DECREASE course quota by 1
      DISPLAY "Registration Successful!"
    ELSE IF quota == 0:
      DISPLAY "Registration Failed: Course is full (No quota left)"
    ELSE:
      DISPLAY "Error: Invalid Course Code"
  ELSE:
    DISPLAY "Login Failed: Invalid ID or Password"
    
  DISPLAY "Session Ended. Goodbye!"
END
