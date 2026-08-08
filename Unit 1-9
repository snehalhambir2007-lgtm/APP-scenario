from dataclasses import dataclass


@dataclass
class Course:
    name: str
    duration: int       # Duration in months
    fee: float

    @property
    def category(self):
        return "Short-Term" if self.duration <= 6 else "Long-Term"


class Institute:
    def __init__(self, name: str):
        self.name = name
        self.courses = []

    def add_course(self, course: Course):
        self.courses.append(course)

    def display_courses(self):
        print(f"\n===== {self.name} =====")
        for course in self.courses:
            print(
                f"Course: {course.name} | "
                f"Duration: {course.duration} months | "
                f"Fee: ₹{course.fee:,.2f} | "
                f"Category: {course.category}"
            )


def main():
    institute = Institute("ABC Institute")

    institute.add_course(Course("Python Programming", 4, 15000))
    institute.add_course(Course("Data Science", 8, 35000))
    institute.add_course(Course("Artificial Intelligence", 12, 50000))

    institute.display_courses()


if __name__ == "__main__":
    main()
