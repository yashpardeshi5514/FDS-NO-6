def quick_sort(arr):
    """Sorts an array of floating-point numbers using Quick Sort."""
    if len(arr) <= 1:
        return arr
    else:
        pivot = arr[0]
        less = [x for x in arr[1:] if x <= pivot]
        greater = [x for x in arr[1:] if x > pivot]
        return quick_sort(less) + [pivot] + quick_sort(greater)

# Function to display top 5 scores
def display_top_five(scores):
    top_five = scores[-5:][::-1]  # Get the top 5 scores in descending order
    print("Top 5 Scores:")
    for score in top_five:
        print(score)

# Input: Array of first-year percentages
student_percentages = []
num_students = int(input("Enter the number of students: "))
print("Enter the percentages of students:")
for _ in range(num_students):
    percentage = float(input())
    student_percentages.append(percentage)

# Sort the array
sorted_percentages = quick_sort(student_percentages)

# Display the sorted percentages
print("Sorted Percentages:")
print(sorted_percentages)

# Display the top five scores
display_top_five(sorted_percentages)
