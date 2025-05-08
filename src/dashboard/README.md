# Dashboard Frontend Overview
<img src="../../assets/ARKTIK%20Logo.png" alt="ARKTIK Logo" width="200">


This folder contains the React-based dashboard application for ARKTIK MicroFarms, delivering real-time data visualization, user controls, and subscription management.

## Directory Structure

```
src/dashboard/
├── components/        # Reusable UI components (charts, cards, forms)
├── pages/             # Route-based page components
│   ├── Home.tsx       # Overview dashboard
│   ├── PlotDetail.tsx # Individual MicroFarm plot view
│   ├── Orders.tsx     # Order history and status
│   ├── Subscriptions.tsx # Subscription management
│   └── Profile.tsx    # User settings and stored-value balance
├── hooks/             # Custom React hooks (useSensors, useAuth)
├── services/          # API clients and data-fetching logic
├── styles/            # Tailwind overrides and global CSS
├── utils/             # Helper functions (formatting, date helpers)
├── App.tsx            # Main application entry with router setup
└── index.tsx          # ReactDOM bootstrap and providers (Auth, Theme)
```

## Key Components

### `components/ChartCard.tsx`

* Displays time-series sensor data using recharts.

### `components/AlertToast.tsx`

* Real-time alert notifications for irrigation, pest, or system issues.

### `components/PlotGrid.tsx`

* Grid layout of all user plots with status indicators and quick actions.

## Pages & Routing

* **Home**: Shows aggregate metrics, recent alerts, and quick links.
* **PlotDetail**: Deep-dive into a single plot’s sensor readings, irrigation control, and AI recommendations.
* **Orders**: Lists past kit purchases, installations, and support packages.
* **Subscriptions**: Allows plan changes, payment updates, and billing history.
* **Profile**: User information, stored-value balance display, and logout.

## Hooks

* **useSensors(plotId)**: Fetches and subscribes to sensor streams via WebSocket or SSE.
* **useAuth()**: Manages JWT token refresh, user context, and route protection.

## Services

* **apiClient.ts**: Configures Axios/Fetch with base URL, interceptors, and error handling.
* **orderService.ts**, **subscriptionService.ts**, **dashboardService.ts**: Implement domain-specific API calls.

## Styling & Theming

* **Tailwind CSS**: Utility-first styling with custom theme extensions (colors: black, Hyper White, gold, silver).
* **Global Styles**: Base typography and spacing in `styles/globals.css`.

## Running Locally

1. **Install dependencies**: `npm install` or `yarn install`
2. **Start dev server**: `npm run start:dashboard`
3. **Environment**: Copy `.env.example` to `.env.local` and configure `REACT_APP_API_URL` and `STRIPE_KEY`.

This dashboard empowers users to monitor, control, and optimize their MicroFarm operations through an intuitive, high-performance interface aligned with ARKTIK’s white-glove luxury learning standards.
