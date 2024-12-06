# Employee Interface CTF Deployment

## Dependencies
[No dependencies for players. The challenge is distributed as a prebuilt executable.]

## First-Time Setup
[For the developer only, not required for players.]

1. Install the necessary dependencies using pip:
    ```bash
    pip install pyinstaller faker
    ```
2. Clone the repository containing the challenge files:
    ```bash
    git clone <repository-url>
    cd <repository-folder>
    ```
3. Generate the database (if not already provided):
    ```bash
    python create_db.py
    ```
4. Package the application into an executable:
    ```bash
    pyinstaller --onefile --add-data "employee.db:." employee_interface.py
    ```

## Starting up the Challenge
For players:
1. Download the provided `employee_interface` executable file.
2. Run the executable directly:
    ```in terminal while in the directory of the challenge
    chmod +x employee_interface
    ./employee_interface
    ```
3. Verify the program starts, and attempt to complete the challenge by retrieving the boss's password.

## Challenge Regeneration
To regenerate the program, a player must re-download a new executable. Should only be applicable if players delete/break the database 

## Publishing the Challenge
Distribute the following file to players by using github https://github.com/js656618/CTF_PROJECT:
- `employee_interface`

