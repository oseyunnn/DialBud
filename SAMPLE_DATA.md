# Sample Data for Google Sheets - User-Specific Structure

## IMPORTANT: All sheets now include Username column to filter data per user

## Sheet: User
Columns: **Username** | Full Name | Email | Phone Number | Date of Birth | Gender | Password | Registration Date

Sample Data:
```
angela123 | Angela Martinez | angela@email.com | +1-555-0123 | 1985-06-15 | female | password123 | 2026-05-18
john_doe | John Doe | john@email.com | +1-555-0124 | 1978-03-22 | male | pass456 | 2026-05-17
```

## Sheet: Session
Columns: **Username** | Date | Time | Duration | Location | Status | Pre-Weight | Post-Weight | Blood Pressure | Notes

**IMPORTANT**: Filter by Username to show only that user's sessions

Sample Data:
```
angela123 | 2026-05-18 | 2:00 PM | 4 hours | City Dialysis Center | Upcoming | - | - | - | Regular session
angela123 | 2026-05-15 | 2:00 PM | 4 hours | City Dialysis Center | Completed | 69.2kg | 68.5kg | 125/82 | Smooth session
angela123 | 2026-05-13 | 2:00 PM | 4 hours | City Dialysis Center | Completed | 70.1kg | 68.8kg | 128/80 | Feeling good
john_doe | 2026-05-18 | 10:00 AM | 4 hours | Memorial Dialysis | Upcoming | - | - | - | Regular session
```

## Sheet: Vitals (Weight & Fluid)
Columns: **Username** | Date | Time | Weight | Fluid Intake | Fluid Limit | Blood Pressure | Heart Rate | Notes

**IMPORTANT**: Filter by Username to show only that user's vitals

Sample Data:
```
angela123 | 2026-05-18 | 8:00 AM | 68.5kg | 1.2L | 1.5L | 120/80 | 72 bpm | Morning measurement
angela123 | 2026-05-17 | 8:00 AM | 68.8kg | 1.3L | 1.5L | 118/78 | 70 bpm | Feeling well
angela123 | 2026-05-16 | 8:00 AM | 69.0kg | 1.4L | 1.5L | 122/79 | 74 bpm | Good day
john_doe | 2026-05-18 | 7:30 AM | 75.2kg | 1.0L | 1.5L | 130/85 | 78 bpm | Morning check
```

## Sheet: Diet
Columns: **Username** | Date | Meal Type | Food Items | Calories | Protein (g) | Potassium (mg) | Phosphorus (mg) | Sodium (mg) | Notes

**IMPORTANT**: Filter by Username to show only that user's diet records

Sample Data:
```
angela123 | 2026-05-18 | Breakfast | Eggs, toast, coffee | 350 | 18 | 245 | 180 | 420 | Low sodium
angela123 | 2026-05-18 | Lunch | Grilled chicken, rice, vegetables | 520 | 35 | 380 | 220 | 550 | Home cooked
angela123 | 2026-05-17 | Dinner | Fish, quinoa, salad | 480 | 32 | 420 | 200 | 480 | Restaurant
john_doe | 2026-05-18 | Breakfast | Oatmeal, banana | 280 | 12 | 320 | 150 | 200 | Healthy start
```

## Sheet: Medications
Columns: **Username** | Medication Name | Dosage | Frequency | Time | Date Started | Status | Notes

**IMPORTANT**: Filter by Username to show only that user's medications

Sample Data:
```
angela123 | Epoetin Alfa | 4000 units | 3x per week | After dialysis | 2026-01-15 | Active | For anemia
angela123 | Calcium Acetate | 667mg | 3x daily | With meals | 2026-01-15 | Active | Phosphate binder
angela123 | Lisinopril | 10mg | Daily | Morning | 2026-01-20 | Active | Blood pressure
angela123 | Vitamin D | 50000 IU | Weekly | Sunday | 2026-02-01 | Active | Supplement
angela123 | Iron Supplement | 325mg | Daily | Evening | 2026-02-10 | Active | For anemia
john_doe | Losartan | 50mg | Daily | Morning | 2026-03-01 | Active | Blood pressure
```

## Sheet: Education
Columns: **Username** | Topic | Title | Date Completed | Duration | Score | Notes

**IMPORTANT**: Filter by Username to show only that user's education records

Sample Data:
```
angela123 | Diet Management | Understanding Potassium in Foods | 2026-05-10 | 15 min | 95% | Very helpful
angela123 | Treatment | How Dialysis Works | 2026-05-05 | 20 min | 88% | Good overview
angela123 | Lifestyle | Exercise Tips for Dialysis Patients | 2026-04-28 | 12 min | 92% | Practical advice
john_doe | Treatment | Managing Your Dialysis Schedule | 2026-05-12 | 18 min | 90% | Great tips
```

## Additional Sheets to Consider:

### Appointments
Columns: **Username** | Date | Time | Doctor | Location | Type | Status | Notes

**IMPORTANT**: Filter by Username to show only that user's appointments

```
angela123 | 2026-05-25 | 10:00 AM | Dr. Smith | Memorial Hospital | Nephrologist | Scheduled | Monthly checkup
angela123 | 2026-05-30 | 2:00 PM | Dr. Johnson | City Clinic | Cardiologist | Scheduled | Heart health
angela123 | 2026-06-02 | 9:00 AM | Dr. Lee | Lab Center | Blood Work | Scheduled | Routine labs
john_doe | 2026-05-28 | 11:00 AM | Dr. Smith | Memorial Hospital | Nephrologist | Scheduled | Follow-up
```

### Lab Results
Columns: **Username** | Date | Test Type | Result | Normal Range | Status | Doctor Notes

**IMPORTANT**: Filter by Username to show only that user's lab results

```
angela123 | 2026-05-10 | Creatinine | 8.2 mg/dL | 0.7-1.3 | High | Monitor closely
angela123 | 2026-05-10 | Hemoglobin | 11.2 g/dL | 12-16 | Low | Continue Epoetin
angela123 | 2026-05-10 | Potassium | 4.8 mEq/L | 3.5-5.0 | Normal | Good control
john_doe | 2026-05-11 | Creatinine | 9.1 mg/dL | 0.7-1.3 | High | Adjust treatment
```

## How to Import This Data:

1. Create these sheet tabs in your Google Sheets:
   - User
   - Session
   - Vitals
   - Diet
   - Medications
   - Education
   - Appointments
   - LabResults

2. Add the column headers in row 1 (make sure **Username** is always the first column)

3. Paste the sample data starting from row 2

4. **CRITICAL**: The dashboard filters all data by the logged-in user's username

5. When querying Google Sheets, always use:
   ```javascript
   WHERE A = 'username'  // Column A is always Username
   ```

6. Users can track their own data which will be added to these sheets with their username automatically
