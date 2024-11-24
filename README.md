
# WebMaster - Convert Website to Mobile App with Admin Dashboard

Welcome to **WebMaster**, a project designed to transform websites into mobile applications with an integrated admin panel for managing your content. Below are the setup and customization instructions for both the **Mobile App** and the **Admin Panel**.  

For more detailed instructions, we recommend that you follow this documentation: [WebMaster Documentation](https://codecrazetech.github.io/webmaster/docs/intro).

---

## Mobile App

### Getting Started

1. **Install Dependencies**  
   Run the following command to install all required dependencies for the project:
   ```bash
   flutter pub get
   ```

2. **Generate Files Using Build Runner**  
   Generate necessary files and resolve any conflicting outputs:
   ```bash
   dart run build_runner build --delete-conflicting-outputs
   ```

3. **Run the App**  
   Launch the application on a connected device or emulator:
   ```bash
   flutter run
   ```

4. **Build the APK**  
   Generate a release-ready APK:
   ```bash
   flutter build apk
   ```

---

### Customizing the Mobile App

1. **Rename the Package**  
   Update the app's package identifier for Android and iOS:
   ```bash
   flutter pub global activate rename
   rename setBundleId --targets android,ios --value "com.your.id.com"
   ```

2. **Change the App Name**  
   Modify the app's display name for both platforms:
   ```bash
   rename setAppName --targets ios,android --value "YourAppName"
   ```

3. **Additional Customizations**  
   Replace icons, themes, and other assets as required in the `assets` directory.

---

## Admin Panel

### Instructions

1. Open the project in **VSCode** or your preferred IDE.

---

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd .\dashboard\
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

---

### Backend Setup

1. Update the API domain:  
   Navigate to `dashboard -> src -> utils -> axios.jsx` and set your local development URL for `API_DOMAIN`.

2. Open the backend directory in your IDE:
   ```bash
   cd .\server\
   ```

3. Create a virtual environment and activate it:
   - **Windows**:
     ```bash
     python -m venv venv
     venv\Scripts\activate
     ```
   - **Linux**:
     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```

4. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```

5. Apply database migrations:
   - **Windows**:
     ```bash
     python manage.py migrate
     ```
   - **Linux**:
     ```bash
     python3 manage.py migrate
     ```

6. Create a superuser for accessing the admin dashboard:
   - **Windows**:
     ```bash
     python manage.py createsuperuser
     ```
   - **Linux**:
     ```bash
     python3 manage.py createsuperuser
     ```

7. Run the development server:
   - **Windows**:
     ```bash
     python manage.py runserver
     ```
   - **Linux**:
     ```bash
     python3 manage.py runserver
     ```

---

### Backend Customization

1. **Firebase Integration**  
   - Download your Firebase JSON file and rename it to `service-account.json`.  
   - Replace the existing `service-account.json` in the `server` directory.  

2. **Update Environment Variables**  
   - Copy the `project_id` from `service-account.json`.  
   - Replace the `project_id` in `server -> .env`.

3. **Development Mode**  
   - Set `DEBUG=True` in the `.env` file for development purposes.

4. **Self-Hosting**  
   - Replace the hostname in `.env` with your desired domain for production hosting.

---

Feel free to reach out with any questions or issues during setup! 🚀
