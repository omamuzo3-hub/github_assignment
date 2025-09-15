def __init__(self, name):
        self.message = f'{name} visitor already exists, No back-to-back entry allowed.'
        super().__init__(self.message)
class TimeRestrictionError(Exception):
    def __init__(self, minutes):
        self.message = f'New entry not allowed until {minutes} minutes have passed since last visitor.'
        super().__init__(self.message)
def main():
    filename = 'visitors.txt'
    # Ensure file exists
    open(filename, 'a').close()
    while True:
        user = input('Enter visitor name (or "q" to quit): ').strip()
        if user.lower() == 'q':
            print("Goodbye!")
            break
        try:
            with open(filename, 'r', encoding='utf-8') as rf:
                lines = rf.readlines()
                if lines:
                    last_name, last_time = lines[-1].strip().split(" | ")
                    last_time = datetime.strptime(last_time, '%Y-%m-%d %H:%M:%S')
                    # Check duplicate
                    if user == last_name:
                        raise DuplicateVisitorError(user)
                    # Check time restriction (3 minutes)
                    if datetime.now() < last_time + timedelta(minutes=3):
                        raise TimeRestrictionError(3)
            # Append if valid
            with open(filename, 'a', encoding='utf-8') as af:
                timestamp = datetime.now().strftime('%Y-%m-%d %H:%M:%S')
                af.write(f'{user} | {timestamp}\n')
            print('Visitor added successfully.')
        except (DuplicateVisitorError, TimeRestrictionError) as e:
            print("Error:", e)
if __name__ == "__main__":
    main()
‎
