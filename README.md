# MemberCard

MemberCard is a React application for displaying a virtual membership card. The current interface is a mobile-first card designed with Plasmic and rendered through React and Vite.

## Card Information

The card interface currently displays the following member attributes:

- Member label: `MEMBRE`
- Last name: `[NOM]`
- First name: `[PRENOM]`
- Registration number: `[MATRICULE]`
- Program or field of study: `[FILIERE]`
- Level: `[NIVEAU]`

The bracketed values are placeholders in the current design and can be replaced with real member data later.

## Technology

- React `18.3.1`
- React DOM `18.3.1`
- Vite
- Plasmic React runtime
- React Aria `3.48.0`
- CSS modules and generated Plasmic styles

React 18 is used because it matches the peer-dependency requirements of the Plasmic runtime and its supporting packages.

## How the Application Loads

The browser starts from `index.html`, which loads `src/main.jsx`. That file mounts the React application and imports `src/App.jsx`.

`App.jsx` loads the virtual-card interface from the local generated component folder:

```jsx
import Homepage from './starter_project_mobile_first/Homepage'

function App() {
  return <Homepage />
}
```

The generated interface and its required local styles are stored in `src/starter_project_mobile_first/`.

`App.jsx` is a React/JSX entry component. It is not intended to be opened directly in a browser as a standalone file; it must be processed by Vite.

## Requirements

- Node.js and npm
- A network connection during the first dependency installation

## Installation

Clone or download the repository, open a terminal in the project directory, and install the dependencies:

```bash
npm install
```

The repository includes `package-lock.json`, so npm can reproduce the pinned dependency versions.

## Run the Application

Start the Vite development server:

```bash
npm run dev
```

Open the local URL printed by Vite, usually `http://localhost:5173`.

## Other Commands

Create a production build:

```bash
npm run build
```

Check the source with ESLint:

```bash
npm run lint
```

Preview the production build locally:

```bash
npm run preview
```

## Project Structure

```text
index.html                         Browser entry document
package.json                       Scripts and dependencies
package-lock.json                  Locked dependency versions
vite.config.js                     Vite configuration
src/main.jsx                       React mounting point
src/App.jsx                        Application component
src/index.css                      Global application styles
src/starter_project_mobile_first/ Virtual-card interface and styles
public/                            Public browser assets
```

## Updating Member Details

The visible placeholder values are defined in the generated Plasmic component at `src/starter_project_mobile_first/PlasmicHomepage.jsx`.

For a production version, member information should be passed as component props or loaded from an API instead of hard-coding it in the generated file. Generated files may be overwritten if the Plasmic design is exported again, so application-specific data logic should preferably live in `Homepage.jsx` or another user-owned component.
