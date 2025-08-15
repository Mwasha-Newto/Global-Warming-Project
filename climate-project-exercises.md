# Global Warming Project - Student Exercises

## Part 1: Data Structures & Basic Operations (Day 1 Concepts)

### Exercise 1.1: Data Structure Modifications
**Difficulty: Easy**
1. Modify the `generate_temperature_data()` function to:
   - Add 5 more cities to the cities list
   - Generate temperature records starting from 1850 instead of 1880
   - Return a dictionary containing all data instead of separate variables

### Exercise 1.2: Tuple Operations
**Difficulty: Easy**
2. Create a function `find_extreme_years()` that:
   - Takes the temperature records as input
   - Returns two tuples: (coldest_year, coldest_temp) and (hottest_year, hottest_temp)
   - Hint: Use min() and max() with key parameter

### Exercise 1.3: Set Operations
**Difficulty: Medium**
3. Write code to:
   - Create a set of years where temperature > 15°C
   - Create a set of years where anomaly > 1°C
   - Find the intersection (years that meet both conditions)
   - Calculate what percentage of total years this represents

### Exercise 1.4: List Comprehension Challenge
**Difficulty: Medium**
4. Using list comprehensions, create:
   - A list of all temperatures converted to Fahrenheit
   - A list of years where the temperature increased from the previous year
   - A nested list structure: [[decade, avg_temp], ...] for each decade

## Part 2: Functions & Lambda (Day 2 Concepts)

### Exercise 2.1: Function Parameters
**Difficulty: Easy**
5. Create a function `analyze_period()` with parameters:
   ```python
   def analyze_period(records, start_year, end_year, metric='mean'):
       # Your code here
   ```
   - Filter records between start_year and end_year
   - Calculate the specified metric (mean, max, min, or std)
   - Return the result with proper error handling

### Exercise 2.2: Lambda Functions
**Difficulty: Medium**
6. Complete these lambda functions:
   ```python
   # Classify warming severity
   classify_anomaly = lambda a: # Return "severe" if >2, "moderate" if >1, else "mild"
   
   # Calculate decade from year
   get_decade = lambda year: # Return the decade (1995 -> 1990)
   
   # Temperature trend indicator
   trend_symbol = lambda current, previous: # Return "↑" if increasing, "↓" if decreasing, "→" if same
   ```

### Exercise 2.3: Higher-Order Functions
**Difficulty: Hard**
7. Create a function that returns a custom filter function:
   ```python
   def create_temp_filter(threshold, comparison='greater'):
       """Returns a filter function based on parameters"""
       # Return a function that filters records based on threshold and comparison type
   ```

## Part 3: NumPy Operations

### Exercise 3.1: Array Creation
**Difficulty: Easy**
8. Create NumPy arrays for:
   - A sine wave representing seasonal temperature variation (365 days)
   - A 2D array (12x10) representing monthly temps for 10 years with random variation
   - Use np.linspace, np.sin, and np.random

### Exercise 3.2: Vectorized Operations
**Difficulty: Medium**
9. WITHOUT using loops, calculate:
   - 5-year moving average of temperatures
   - Z-scores for all temperature values
   - Percentile rank for each year's temperature
   ```python
   # Hint structure:
   temps_array = np.array([r[1] for r in records])
   # Calculate moving average using array slicing
   # Z-score = (value - mean) / std
   ```

### Exercise 3.3: Boolean Indexing
**Difficulty: Medium**
10. Using boolean indexing on NumPy arrays:
    - Find all years where temp is above 1 std deviation from mean
    - Extract temperatures for El Niño years (every 3-7 years pattern)
    - Create a masked array hiding "outlier" temperatures

### Exercise 3.4: Statistical Analysis
**Difficulty: Hard**
11. Implement warming acceleration analysis:
    ```python
    def calculate_acceleration(temps_array, window=10):
        """Calculate rate of change of warming rate"""
        # Calculate first derivative (rate of change)
        # Calculate second derivative (acceleration)
        # Return periods of accelerating vs decelerating warming
    ```

## Part 4: Integration Challenges

### Exercise 4.1: City Impact Enhancements
**Difficulty: Medium**
12. Extend the `simulate_city_impacts()` function to:
    - Add latitude as a factor (higher latitudes warm more)
    - Include sea level (coastal cities have different warming patterns)
    - Return a NumPy structured array instead of list of dicts

### Exercise 4.2: Projection Model
**Difficulty: Hard**
13. Create a function that projects future temperatures:
    ```python
    def project_future(records, years_ahead=30, scenario='moderate'):
        """
        Project future temperatures based on historical trends
        Scenarios: 'optimistic' (slower warming), 'moderate', 'pessimistic' (faster)
        """
        # Use np.polyfit for trend analysis
        # Apply scenario multiplier
        # Add random variation based on historical volatility
        # Return projected years and temperatures
    ```

### Exercise 4.3: Data Validation
**Difficulty: Medium**
14. Add data validation to the temperature generation:
    - Check for unrealistic temperatures (<-10°C or >20°C global average)
    - Identify and flag potential data errors (sudden jumps >2°C)
    - Calculate confidence intervals for decade averages

## Part 5: Debugging Exercises

### Exercise 5.1: Fix the Bugs
**Difficulty: Easy-Medium**
15. Debug this broken code:
    ```python
    def calculate_trend(records):
        temps = [r[1] for r in records]
        years = [r[0] for r in records]
        
        # Bug 1: Wrong calculation
        trend = np.sum(temps) / np.sum(years)
        
        # Bug 2: Index error
        warmest_decade = decades[np.argmax(decade_avgs)]
        
        # Bug 3: Type error
        above_average = temps > np.mean(temps)
        
        return trend, warmest_decade, above_average
    ```

### Exercise 5.2: Performance Optimization
**Difficulty: Hard**
16. This function is slow. Optimize it using NumPy:
    ```python
    def slow_analysis(records):
        result = []
        for i in range(len(records)):
            total = 0
            count = 0
            for j in range(max(0, i-5), min(len(records), i+6)):
                total += records[j][1]
                count += 1
            result.append(total / count)
        return result
    ```

## Part 6: Creative Extensions

### Exercise 6.1: Visualization Prep
**Difficulty: Medium**
17. Prepare data for visualization (without plotting):
    - Create bins for temperature ranges and count occurrences
    - Calculate correlation between year and temperature
    - Generate data for a heatmap: decades vs months average temps

### Exercise 6.2: Custom Analysis
**Difficulty: Open-ended**
18. Choose ONE to implement:
    - A. Detect "climate events" (unusual temperature patterns)
    - B. Compare warming rates across different time periods
    - C. Create a "climate risk score" combining multiple factors
    - D. Implement seasonal decomposition (trend + seasonal + residual)

## Part 7: Comprehensive Challenge

### Exercise 7.1: Build Your Own Climate Analyzer
**Difficulty: Hard**
19. Create a class `ClimateAnalyzer` that:
    ```python
    class ClimateAnalyzer:
        def __init__(self, records):
            # Initialize with records
            # Convert to NumPy arrays
            # Calculate basic statistics
        
        def get_decade_summary(self, decade):
            # Return comprehensive decade analysis
        
        def compare_periods(self, period1, period2):
            # Compare two time periods
        
        def find_tipping_points(self):
            # Identify significant change points
        
        def generate_report(self):
            # Return formatted analysis report
    ```

### Exercise 7.2: Error Handling
**Difficulty: Medium**
20. Add comprehensive error handling:
    - Handle empty datasets
    - Validate year ranges
    - Check for data consistency
    - Provide meaningful error messages

## Bonus Challenges

### Bonus 1: Memory Efficiency
Compare memory usage between lists and NumPy arrays for 1 million temperature records.

### Bonus 2: Algorithm Implementation
Implement the Mann-Kendall trend test to determine if warming trend is statistically significant.

### Bonus 3: Real Data Integration
Modify the code to read actual climate data from a CSV file (create sample CSV first).

---

## Answer Key Guidelines

**For instructors**: 
- Exercises 1-4: Test basic understanding (15-20 min each)
- Exercises 5-11: Build proficiency (20-30 min each)
- Exercises 12-16: Apply knowledge (30-45 min each)
- Exercises 17-20: Demonstrate mastery (45-60 min each)

**Grading suggestions**:
- Correct output: 40%
- Code quality: 30%
- Efficiency: 20%
- Documentation: 10%

**Common pitfalls to watch for**:
- Forgetting to handle edge cases
- Using loops instead of vectorization
- Not validating input data
- Incorrect indexing in slicing operations
- Type mismatches between lists and arrays