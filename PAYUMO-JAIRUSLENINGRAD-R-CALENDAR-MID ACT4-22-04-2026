class Calendar:

    def __init__(self):
        self.events = {}

    def is_leap_year(self, year):
        if year % 4 == 0:
            return True
        else:
            return False

    def get_days_in_month(self, month, year):
        match month:
            case 1:
                return 31
            case 2:
                if self.is_leap_year(year):
                    return 29
                else:
                    return 28
            case 3:
                return 31
            case 4:
                return 30
            case 5:
                return 31
            case 6:
                return 30
            case 7:
                return 31
            case 8:
                return 31
            case 9:
                return 30
            case 10:
                return 31
            case 11:
                return 30
            case 12:
                return 31
            case _:
                return -1

    def get_month_name(self, month):
        match month:
            case 1:
                return "January"
            case 2:
                return "February"
            case 3:
                return "March"
            case 4:
                return "April"
            case 5:
                return "May"
            case 6:
                return "June"
            case 7:
                return "July"
            case 8:
                return "August"
            case 9:
                return "September"
            case 10:
                return "October"
            case 11:
                return "November"
            case 12:
                return "December"
            case _:
                return "Unknown"

    def is_valid_date(self, day, month, year):
        if year < 2026 or year > 2028:
            print("[ERROR] Year must be between 2026 and 2028 only!")
            return False

        if month < 1 or month > 12:
            print("[ERROR] Month must be between 1 and 12 only!")
            return False

        max_days = self.get_days_in_month(month, year)

        if day < 1 or day > max_days:
            print(f"[ERROR] Day must be between 1 and {max_days} for {self.get_month_name(month)} {year}!")
            return False

        return True

    def make_date_key(self, day, month, year):
        return f"{year}-{month:02d}-{day:02d}"

    def add_event(self, day, month, year, event_name):
        if not self.is_valid_date(day, month, year):
            return

        key = self.make_date_key(day, month, year)

        if key in self.events:
            self.events[key].append(event_name)
        else:
            self.events[key] = [event_name]

        print(f"\n[SUCCESS] Event '{event_name}' added on {self.get_month_name(month)} {day}, {year}!")

    def view_events_on_date(self, day, month, year):
        key = self.make_date_key(day, month, year)

        if key in self.events:
            print(f"\nEvents on {self.get_month_name(month)} {day}, {year}:")
            for i, event in enumerate(self.events[key]):
                print(f"{i+1}. {event}")
        else:
            print(f"\nNo events found for {self.get_month_name(month)} {day}, {year}")


cal = Calendar()

while True:
    print("\n---- MAIN MENU----")
    print("1. Add an Event")
    print("2. View Events on a Date")
    print("3. View All Events")
    print("4. Delete an Event")
    print("5. Exit")

    choice = input("\nEnter your choice (1-5): ")

    if choice == "1":
        print("\n---- ADD AN EVENT ----")
        print("Enter the date:")

        y = int(input("Year (2026-2028): "))
        m = int(input("Month (1-12): "))
        d = int(input("Day: "))
        name = input("Enter event name: ")

        cal.add_event(d, m, y, name)

    elif choice == "5":
        print("Thank you!")
        break
