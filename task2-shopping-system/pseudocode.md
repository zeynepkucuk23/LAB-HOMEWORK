START ONLINE_SHOPPING_SYSTEM
    DISPLAY "Welcome to E-Shop"
    
    // User Login Check
    INPUT credentials
    IF login_is_valid THEN
        START SHOPPING_LOOP
            REPEAT
                DISPLAY "1. Browse Categories, 2. View Cart, 3. Checkout, 4. Logout"
                INPUT user_choice
                
                IF user_choice == 1 THEN
                    START CATEGORY_LOOP
                        DISPLAY "Available Categories: Electronics, Fashion, Home"
                        INPUT category_choice
                        DISPLAY "Products in " + category_choice
                        INPUT product_to_add
                        
                        // Stock Availability Check
                        IF product_in_stock THEN
                            ADD product_to_add TO cart
                            DISPLAY "Added to cart"
                        ELSE
                            DISPLAY "Sorry, out of stock"
                        END IF
                    END CATEGORY_LOOP
                    
                ELSE IF user_choice == 2 THEN
                    START VIEW_CART_LOOP
                        DISPLAY items_in_cart
                        INPUT edit_action (Remove/Update/None)
                        IF edit_action != None THEN
                            UPDATE cart_contents
                        END IF
                    END VIEW_CART_LOOP
                    
                ELSE IF user_choice == 3 THEN
                    // Checkout Process
                    IF cart_total < 10 THEN
                        DISPLAY "Minimum order amount is $10. Please add more items."
                    ELSE
                        // Discount Code Check
                        INPUT discount_code
                        IF discount_code == "SAVE10" THEN
                            APPLY 10% discount
                        END IF
                        
                        // Shipping Fee Calculation
                        IF cart_total > 40 THEN
                            shipping_fee = 0
                            DISPLAY "Free shipping applied!"
                        ELSE
                            shipping_fee = 5
                        END IF
                        
                        // Payment and Confirmation
                        DISPLAY "Select Payment Method: 1. Credit Card, 2. PayPal"
                        INPUT payment_method
                        DISPLAY "Processing payment..."
                        DISPLAY "Order Confirmed! Receipt sent to email."
                        EMPTY cart
                        EXIT SHOPPING_LOOP
                    END IF
                END IF
            UNTIL user_choice == 4
        END SHOPPING_LOOP
    ELSE
        DISPLAY "Invalid Login. Access Denied."
    END IF
END ONLINE_SHOPPING_SYSTEM
