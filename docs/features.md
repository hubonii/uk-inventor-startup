# Feature Specification

## Feature 1: The Camera Sandbox
- **Description:** A custom camera view that intercepts the image buffer.
- **Why:** Prevents couriers/senders from saving sensitive photos of package contents or IDs to their personal iCloud/Google Photos.

## Feature 2: Anti-Hoarding Geofence
- **Description:** If a courier accepts a package but does not leave a 200-meter radius of the pickup location within 15 minutes, an automated warning is fired.
- **Why:** Prevents couriers from taking 10 packages and sitting in a coffee shop, destroying SLA times.

## Feature 3: Dynamic Surge Pricing
- **Description:** If a package is unaccepted, the platform slowly diverts its £1-£2 margin into the Courier Payout. 
- **Why:** Ensures clearing of the marketplace without charging the Sender more money post-checkout.

## 📝 Remaining Unknowns (TODOs)
- **Push Notification Reliability:** Investigate how aggressive battery-saving modes on Chinese Android OEMs (Xiaomi, Huawei) will kill our background GPS tracking service.
