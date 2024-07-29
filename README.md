# Svelte FormWizard

Simplifying form management in Svelte with Firebase Firestore integration.

## Introduction

FormWizard is an open-source project designed to streamline the creation and management of forms in a Svelte application, with seamless integration to Firebase Firestore. This project provides a collection of reusable form components, making it easy to collect and store data.

## Key Features

- **Reusable Components**: Create forms for various services with ease using the provided reusable components.
- **Seamless Firestore Integration**: Automatically save form data to Firebase Firestore, ensuring a reliable and scalable data storage solution.
- **Customizable Fields**: Define custom fields for each form, including text inputs, textareas, selects, and file uploads.
- **Prevent Duplicate Code**: Use a generic form component to handle different input types and form configurations, reducing code redundancy.

## Getting Started

### Prerequisites

Before you start, ensure you have the following:

- A Svelte application
- A Firebase project with Firestore enabled

### Installation

First, clone the FormWizard repository:

```bash
git clone https://github.com/your-username/formwizard.git
```

Then, navigate to the project directory and install the dependencies:

```bash
cd formwizard
npm install
```
### Configuration
Set up your Firebase configuration in src/firebase.js:

```javascript
import { initializeApp } from "firebase/app";
import { getFirestore } from "firebase/firestore";

const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID"
};

const app = initializeApp(firebaseConfig);
export const firestore = getFirestore(app);
```
# Creating a Form
To create a form for a specific service, you’ll use the generic form component provided by FormWizard. For example, let’s create a form for “Logo and Brand Identity” services:

```svelte
<script>
  import GenericForm from './components/Forms/GenericForm.svelte';

  const formFields = [
    { name: 'name', label: 'Name', type: 'text' },
    { name: 'email', label: 'Email', type: 'email' },
    { name: 'businessName', label: 'Business Name', type: 'text' },
    { name: 'logoDescription', label: 'Logo Description', type: 'textarea' },
    { name: 'brandColors', label: 'Brand Colors', type: 'text' },
    { name: 'fileUpload', label: 'File Upload', type: 'file' }
  ];
  const collectionName = 'logoBrandIdentity';
</script>

<GenericForm {formFields} {collectionName} />
```

This component will automatically handle the form submission and save the data to the specified Firestore collection.

# Contributing
Svelte FormWizard is an open-source project and contributions are welcome!
