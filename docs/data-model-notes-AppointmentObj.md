
Fields Used in Appointment Object-

## 1-Date (Fieldtype- Date)

## 2- Start Time (Fieldtype-Time)

## 3-End Time (Fieldtype- Formula)
End Time Formula

End Time on the Appointment object is a formula field that 
auto-calculates from Start Time + Doctor's slot duration.

Formula: Start_Time__c + (Doctor__r.Slot_Duration__c / 1440)

Why: Salesforce stores Time fields as decimal fractions of a 
24-hour day. 1440 = total minutes in a day. Dividing slot 
duration by 1440 converts minutes into the correct decimal 
fraction to add to the start time.

Example: 2:00 PM start + 30 min slot = 2:00 PM (0.5833) + 
0.0208 = 0.6041 = 2:30 PM end time.

Doctor__r notation is a cross-object formula — it traverses 
the lookup relationship from Appointment to Doctor to read 
the Slot Duration field directly.

## 4- Doctor (Fieldtype- Lookup, On Doctor Obj)

## 5- Patient (Fieldtype- Lookup, On Patient Obj)

## 6- Status (Fieldtype- Picklist, for the status of appointment record)

## 7- Notes (Fieldtype- Text(Long))
