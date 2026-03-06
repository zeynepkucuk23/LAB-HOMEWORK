START
  DISPLAY "Welcome to the Hospital Management System"
  INPUT "Enter Patient Name and ID"
  
  DISPLAY "Select Department: 1. Cardiology, 2. Pediatrics, 3. General Surgery"
  INPUT department_choice
  
  IF doctor is available for department_choice:
    DISPLAY "Available Slots: 09:00, 10:30, 14:00"
    INPUT "Select a time slot"
    CONFIRM "Appointment booked successfully!"
  ELSE:
    DISPLAY "No available doctors at the moment."
  
  PRINT "Thank you for using our system."
END
