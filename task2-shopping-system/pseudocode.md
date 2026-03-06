BEGIN
  Total_Cart = 0
  WHILE (Customer wants to add more items)
    INPUT "Enter Item Name:" Item_Name
    INPUT "Enter Item Price:" Item_Price
    INPUT "Enter Quantity:" Quantity
    Subtotal = Item_Price * Quantity
    Total_Cart = Total_Cart + Subtotal
    OUTPUT Item_Name + " added to cart."
  END WHILE
  
  IF Total_Cart > 1000 THEN
    Total_Cart = Total_Cart * 0.9  // 10% discount
  END IF
  
  OUTPUT "Final Total: " + Total_Cart
END
