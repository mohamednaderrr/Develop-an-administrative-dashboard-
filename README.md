## Testing the Admin Dashboard

**Admin User:**

1.  Ensure your user context or mock setup returns `isAdmin: true` for the user you are testing with.
2.  Navigate to the `/admin` route in your application (e.g., `http://localhost:3000/admin`).
3.  You should see the Admin Dashboard with the key stats (either real data if the API is connected or placeholder data).
4.  Locate the "Maintenance Mode" toggle.
5.  Toggle the switch. You should see the "Maintenance is ON" or "OFF" text update.
6.  If the .NET Dev #5 API is ready and `isMaintenanceToggleReady` is set to `true`, verify in your browser's Network tab that a POST request is sent to `/api/admin/maintenance/toggle` when you toggle the switch.

**Non-Admin User:**

1.  Ensure your user context or mock setup returns `isAdmin: false` for the user you are testing with.
2.  Navigate to the `/admin` route in your application.
3.  You should be either:
    - Redirected to the home page (`/`).
    - See the "Access Denied" page with the appropriate message
