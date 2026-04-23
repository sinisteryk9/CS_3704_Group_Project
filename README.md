# ShelfLife

ShelfLife is an intelligent kitchen assistant designed to minimize food waste and optimize your cooking experience. By tracking inventory, expiration dates, and nutritional goals, ShelfLife helps you make the most of what you have.

---

## Core Features
- **Smart Inventory:** Barcode scanning and manual entry for ingredient tracking.
- **AI Tools:** Automatic grocery list generation and taste-based recipe suggestions.
- **Community Modes:** Downloadable "modes" created by the community to customize app behavior.
- **Shop Locator:** Integrated map functionality to find missing ingredients nearby.

---

## Use Cases

### **Account & Security**
| UC# | Use Case | Description |
| :--- | :--- | :--- |
| **UC3** | Security Settings | Manage password resets, recovery emails, and 2FA. |
| **UC16** | Profile Management | Configure dietary preferences and allergen settings. |
| **UC19** | Account Creation | Secure user registration process. |
| **UC20** | Login / Logout | Secure session management for users. |

### **Inventory & Tracking**
| UC# | Use Case | Description |
| :--- | :--- | :--- |
| **UC4** | Offline Mode | View and edit inventory using local cache when offline. |
| **UC7** | Barcode Scanner | Add items to inventory by scanning barcodes. |
| **UC11** | Labels & Tags | Create and attach custom labels to recipes or ingredients. |
| **UC13** | Manual Entry | Manually add ingredients to the digital inventory. |

### **Meal Planning & Recipes**
| UC# | Use Case | Description |
| :--- | :--- | :--- |
| **UC5** | AI Generator | Create weekly meal plans and grocery lists automatically. |
| **UC6** | Eat Meal Reminders | Automated notifications to help follow a meal schedule. |
| **UC10** | Calorie Intake | Set and track daily/monthly caloric consumption levels. |
| **UC12** | Dashboard | Central view of expiring items and recommended recipes. |
| **UC15** | Cookbook Management | Search, edit, and organize personal recipe collections. |

### **Community & Support**
| UC# | Use Case | Description |
| :--- | :--- | :--- |
| **UC1** | About Us | View the app mission, analytics, and donation links. |
| **UC8** | Contact Us | Submit bug reports and support inquiries. |
| **UC9** | Modes Library | Browse, upload, or download user-created app modes. |
| **UC14** | Shop Locator | Find stores nearby for missing ingredients (Google Maps). |
| **UC17** | User Forum | Discuss recipes and tips in a community forum. |
| **UC18** | Help Guide | Access official documentation and user guides. |

### **Analytics**
| UC# | Use Case | Description |
| :--- | :--- | :--- |
| **UC2** | History & Stats | View graphs of food consumption and waste patterns. |

---
# Algorithms Implemented

ShelfLife includes algorithm-driven workflows that power core system functionality.

## Community & Modes
- `uploadMode()` – Uploads or updates community-created modes.
- `downloadMode()` – Retrieves downloadable mode data.
- `fetchModes()` – Loads publicly available modes.

## Store Discovery
- `findNearbyStores()` – Finds stores carrying missing ingredients.

## Community Interaction
- `postForumIssue()` – Creates a new forum post.
- `replyToPost()` – Allows threaded replies to discussions.

## Notifications
- `manageReminder()` – Creates, snoozes, cancels, and schedules reminders.

## Nutrition & Personalization
- `setDailyCalorieGoal()` – Calculates and validates calorie goals.
- `manageAccountPreferences()` – Handles allergens, password resets, and 2FA.

## Inventory & Labels
- `addGroceryItem()` – Adds grocery items with validation.
- `manageFoodLabel()` – Creates, attaches, or removes labels.
- `scanBarcode()` – Uses barcode APIs to autofill grocery entries.

## Recipes & Meal Planning
- `generateRecipeMatches()` – Matches recipes to inventory.
- `saveRecipe()` – Saves recipes to a personal cookbook.
- `addRecipeToMealPlan()` – Adds recipes to meal schedules.
- `searchCookbook()` – Searches recipes by ingredients or title.
- `editRecipe()` – Updates user cookbook entries.
- `getMissingIngredients()` – Finds unavailable ingredients for recipes.

## Authentication
- `login()` – Validates credentials and starts a session.
- `logout()` – Terminates sessions.
- `createAccount()` – Registers new users securely.

---

# Database Schema

ShelfLife uses a relational database structure to organize persistent application data.

## Core Tables

### Users
Stores authentication and account details.

Fields:
- user_id
- full_name
- username
- email
- password_hash

### User Preferences
Stores dietary preferences and restrictions.

Fields:
- preference_id
- user_id
- diet_type
- allergy_notes
- budget_limit

### Grocery Items
Tracks user inventory.

Fields:
- grocery_item_id
- user_id
- ingredient_type_id
- item_name
- quantity
- calorie_amount
- grocery_cost
- expiration_date

### Recipes
Stores recipe information.

Fields:
- recipe_id
- title
- source_name
- instructions
- estimated_cost

### Saved Recipes
Links users to stored recipes.

Fields:
- saved_recipe_id
- user_id
- recipe_id
- saved_at

### Meal Plans
Stores planned meals over time.

Fields:
- meal_plan_id
- user_id
- plan_name
- start_date
- end_date

### Notifications
Stores reminder and alert information.

Fields:
- notification_id
- user_id
- message_text
- notification_type
- created_at
- is_read

### Ingredient Types
Defines supported ingredient categories.

Examples:
- Vegetables
- Fruits
- Dairy
- Protein
- Grains

---
# Entity Relationships

Major system relationships include:

- A user has many grocery items.
- A user has many saved recipes.
- A user has many notifications.
- A user has one preference profile.
- Meal plans belong to users.
- Grocery items connect to ingredient types.
- Meal plans contain scheduled recipes.
- Modes may contain multiple meal plans.

---

# Non-Functional Requirements

- Inventory should load within 10 seconds.
- User authentication should complete within 5 seconds.
- UI should support accessibility standards.
- Screen-reader compatibility should be supported.
- Colorblind accessibility mode should be available.
- Background actions should provide visual feedback.
- Input validation and sanitization should be enforced.

---

# Future Expansion Opportunities

Potential future improvements include:

- AI-powered shopping optimization.
- Nutritional scoring and health insights.
- Recipe recommendation personalization.
- Expanded analytics dashboard.
- Smart kitchen integrations.
- Push notifications across devices.
- Cloud synchronization enhancements.
- Mobile-first UI deployment.

---

# Technology Concepts

ShelfLife combines multiple software engineering concepts:

- Object-oriented design
- Database normalization
- API integration
- Authentication systems
- CRUD operations
- Recommendation systems
- Notification scheduling
- Community content management
- Offline caching

---
