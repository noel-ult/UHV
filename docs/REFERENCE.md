# UHV source reference


Source reviewed: [`32c659e742f3`](https://github.com/noel-ult/UHV/commit/32c659e742f3a930c2fc15a6dcb83dc8be4f61e6).

This reference records the checked-in source, scripts, configuration names, and route declarations. It is a navigation aid; service availability and successful test execution require separate verification.

## Package commands

Run each command in the directory containing its package manifest. A declared script is not necessarily a passing check; guides call out placeholders and known mismatches.

### backend/package.json

| Script | Shell command |
| --- | --- |
| `start` | `node src/server.js` |
| `dev` | `nodemon src/server.js` |
| `init-db` | `node src/config/initDatabase.js` |
| `test` | `echo "Error: no test specified" && exit 1` |

Manifest: [backend/package.json](../backend/package.json).

### package.json

| Script | Shell command |
| --- | --- |
| `dev` | `vite` |
| `build` | `tsc && vite build` |
| `preview` | `vite preview` |
| `lint` | `tsc --noEmit` |

Manifest: [package.json](../package.json).

## Configuration names

Names below are declared by source or example files. Example-only entries may be stale; consult the linked reader and project guide before relying on them. Secret values are intentionally omitted.

| Name | Declared/read in |
| --- | --- |
| `DATABASE_URL` | [backend/src/config/database.js](../backend/src/config/database.js) |
| `DB_POOL_CONNECTION_TIMEOUT` | [backend/src/config/database.js](../backend/src/config/database.js) |
| `DB_POOL_IDLE_TIMEOUT` | [backend/src/config/database.js](../backend/src/config/database.js) |
| `DB_POOL_MAX` | [backend/src/config/database.js](../backend/src/config/database.js) |
| `DB_POOL_MIN` | [backend/src/config/database.js](../backend/src/config/database.js) |
| `FRONTEND_URL` | [backend/.env.example](../backend/.env.example), [backend/src/server.js](../backend/src/server.js) |
| `JWT_SECRET` | [backend/.env.example](../backend/.env.example), [backend/src/middleware/auth.js](../backend/src/middleware/auth.js), [backend/src/routes/auth.js](../backend/src/routes/auth.js) |
| `MAX_FILE_SIZE` | [backend/.env.example](../backend/.env.example) |
| `MONGODB_URI` | [backend/.env.example](../backend/.env.example) |
| `NODE_ENV` | [backend/.env.example](../backend/.env.example), [backend/src/server.js](../backend/src/server.js) |
| `PORT` | [backend/.env.example](../backend/.env.example), [backend/src/server.js](../backend/src/server.js) |
| `VITE_API_URL` | [src/lib/api.ts](../src/lib/api.ts) |

## HTTP route declarations

Paths are **as declared in each source file**. Router/blueprint mount prefixes from the entry point must be prepended; the project guide describes the active entry point and common prefixes. Alternate entry points (such as SQLite) are listed separately by file. Authentication, request bodies, and response schemas live in the linked handlers/models.

| Source | Method | Declared path | Handler |
| --- | --- | --- | --- |
| [backend/src/routes/auth.js](../backend/src/routes/auth.js) | POST | `/register` | `` |
| [backend/src/routes/auth.js](../backend/src/routes/auth.js) | POST | `/login` | `` |
| [backend/src/routes/auth.js](../backend/src/routes/auth.js) | GET | `/me` | `` |
| [backend/src/routes/auth.js](../backend/src/routes/auth.js) | PUT | `/profile` | `` |
| [backend/src/routes/issues.js](../backend/src/routes/issues.js) | POST | `/` | `` |
| [backend/src/routes/issues.js](../backend/src/routes/issues.js) | GET | `/` | `` |
| [backend/src/routes/issues.js](../backend/src/routes/issues.js) | GET | `/my-issues` | `` |
| [backend/src/routes/issues.js](../backend/src/routes/issues.js) | GET | `/stats/overview` | `` |
| [backend/src/routes/issues.js](../backend/src/routes/issues.js) | GET | `/:id` | `` |
| [backend/src/routes/issues.js](../backend/src/routes/issues.js) | PUT | `/:id` | `` |
| [backend/src/routes/issues.js](../backend/src/routes/issues.js) | DELETE | `/:id` | `` |
| [backend/src/routes/issues.js](../backend/src/routes/issues.js) | PUT | `/:id/status` | `` |
| [backend/src/routes/issues.js](../backend/src/routes/issues.js) | PUT | `/:id/assign` | `` |
| [backend/src/routes/issues.js](../backend/src/routes/issues.js) | POST | `/:id/comments` | `` |
| [backend/src/routes/issues.js](../backend/src/routes/issues.js) | GET | `/:id/comments` | `` |
| [backend/src/routes/notices.js](../backend/src/routes/notices.js) | POST | `/` | `` |
| [backend/src/routes/notices.js](../backend/src/routes/notices.js) | GET | `/` | `` |
| [backend/src/routes/notices.js](../backend/src/routes/notices.js) | GET | `/:id` | `` |
| [backend/src/routes/notices.js](../backend/src/routes/notices.js) | PUT | `/:id` | `` |
| [backend/src/routes/notices.js](../backend/src/routes/notices.js) | DELETE | `/:id` | `` |
| [backend/src/routes/users.js](../backend/src/routes/users.js) | GET | `/` | `` |
| [backend/src/routes/users.js](../backend/src/routes/users.js) | GET | `/:id` | `` |
| [backend/src/routes/users.js](../backend/src/routes/users.js) | PUT | `/:id/role` | `` |
| [backend/src/routes/users.js](../backend/src/routes/users.js) | PUT | `/:id/status` | `` |
| [backend/src/routes/users.js](../backend/src/routes/users.js) | GET | `/stats/overview` | `` |
| [backend/src/server.js](../backend/src/server.js) | GET | `/api/health` | `` |

## Existing documentation

Historical plans/reports describe their own revision; use current source when they disagree.

- [PROJECT_STRUCTURE.md](../PROJECT_STRUCTURE.md)
- [README.md](../README.md)
- [TESTING_GUIDE.md](../TESTING_GUIDE.md)
- [backend/README.md](../backend/README.md)

## Source and configuration map

Generated lockfiles, binary assets, compiled output, vendored dependencies, and cached bytecode are omitted. Test files remain listed so coverage can be located.

- [.env.example](../.env.example)
- [.vscode/extensions.json](../.vscode/extensions.json)
- [backend/.env.example](../backend/.env.example)
- [backend/addNotices.js](../backend/addNotices.js)
- [backend/make-admin.sql](../backend/make-admin.sql)
- [backend/package.json](../backend/package.json)
- [backend/postman_collection.json](../backend/postman_collection.json)
- [backend/resetDb.js](../backend/resetDb.js)
- [backend/src/config/database.js](../backend/src/config/database.js)
- [backend/src/config/initDatabase.js](../backend/src/config/initDatabase.js)
- [backend/src/config/schema.sql](../backend/src/config/schema.sql)
- [backend/src/middleware/auth.js](../backend/src/middleware/auth.js)
- [backend/src/models/Comment.js](../backend/src/models/Comment.js)
- [backend/src/models/Issue.js](../backend/src/models/Issue.js)
- [backend/src/models/Notice.js](../backend/src/models/Notice.js)
- [backend/src/models/User.js](../backend/src/models/User.js)
- [backend/src/routes/auth.js](../backend/src/routes/auth.js)
- [backend/src/routes/issues.js](../backend/src/routes/issues.js)
- [backend/src/routes/notices.js](../backend/src/routes/notices.js)
- [backend/src/routes/users.js](../backend/src/routes/users.js)
- [backend/src/server.js](../backend/src/server.js)
- [backend/test-data.sql](../backend/test-data.sql)
- [backend/update-constraints.sql](../backend/update-constraints.sql)
- [index.html](../index.html)
- [package.json](../package.json)
- [postcss.config.js](../postcss.config.js)
- [src/App.tsx](../src/App.tsx)
- [src/components/Footer.tsx](../src/components/Footer.tsx)
- [src/components/Navbar.tsx](../src/components/Navbar.tsx)
- [src/components/figma/ImageWithFallback.tsx](../src/components/figma/ImageWithFallback.tsx)
- [src/components/ui/accordion.tsx](../src/components/ui/accordion.tsx)
- [src/components/ui/alert-dialog.tsx](../src/components/ui/alert-dialog.tsx)
- [src/components/ui/alert.tsx](../src/components/ui/alert.tsx)
- [src/components/ui/aspect-ratio.tsx](../src/components/ui/aspect-ratio.tsx)
- [src/components/ui/avatar.tsx](../src/components/ui/avatar.tsx)
- [src/components/ui/badge.tsx](../src/components/ui/badge.tsx)
- [src/components/ui/breadcrumb.tsx](../src/components/ui/breadcrumb.tsx)
- [src/components/ui/button.tsx](../src/components/ui/button.tsx)
- [src/components/ui/calendar.tsx](../src/components/ui/calendar.tsx)
- [src/components/ui/card.tsx](../src/components/ui/card.tsx)
- [src/components/ui/carousel.tsx](../src/components/ui/carousel.tsx)
- [src/components/ui/chart.tsx](../src/components/ui/chart.tsx)
- [src/components/ui/checkbox.tsx](../src/components/ui/checkbox.tsx)
- [src/components/ui/collapsible.tsx](../src/components/ui/collapsible.tsx)
- [src/components/ui/command.tsx](../src/components/ui/command.tsx)
- [src/components/ui/context-menu.tsx](../src/components/ui/context-menu.tsx)
- [src/components/ui/dialog.tsx](../src/components/ui/dialog.tsx)
- [src/components/ui/drawer.tsx](../src/components/ui/drawer.tsx)
- [src/components/ui/dropdown-menu.tsx](../src/components/ui/dropdown-menu.tsx)
- [src/components/ui/form.tsx](../src/components/ui/form.tsx)
- [src/components/ui/hover-card.tsx](../src/components/ui/hover-card.tsx)
- [src/components/ui/input-otp.tsx](../src/components/ui/input-otp.tsx)
- [src/components/ui/input.tsx](../src/components/ui/input.tsx)
- [src/components/ui/label.tsx](../src/components/ui/label.tsx)
- [src/components/ui/menubar.tsx](../src/components/ui/menubar.tsx)
- [src/components/ui/navigation-menu.tsx](../src/components/ui/navigation-menu.tsx)
- [src/components/ui/pagination.tsx](../src/components/ui/pagination.tsx)
- [src/components/ui/popover.tsx](../src/components/ui/popover.tsx)
- [src/components/ui/progress.tsx](../src/components/ui/progress.tsx)
- [src/components/ui/radio-group.tsx](../src/components/ui/radio-group.tsx)
- [src/components/ui/resizable.tsx](../src/components/ui/resizable.tsx)
- [src/components/ui/scroll-area.tsx](../src/components/ui/scroll-area.tsx)
- [src/components/ui/select.tsx](../src/components/ui/select.tsx)
- [src/components/ui/separator.tsx](../src/components/ui/separator.tsx)
- [src/components/ui/sheet.tsx](../src/components/ui/sheet.tsx)
- [src/components/ui/sidebar.tsx](../src/components/ui/sidebar.tsx)
- [src/components/ui/skeleton.tsx](../src/components/ui/skeleton.tsx)
- [src/components/ui/slider.tsx](../src/components/ui/slider.tsx)
- [src/components/ui/sonner.tsx](../src/components/ui/sonner.tsx)
- [src/components/ui/switch.tsx](../src/components/ui/switch.tsx)
- [src/components/ui/table.tsx](../src/components/ui/table.tsx)
- [src/components/ui/tabs.tsx](../src/components/ui/tabs.tsx)
- [src/components/ui/textarea.tsx](../src/components/ui/textarea.tsx)
- [src/components/ui/toggle-group.tsx](../src/components/ui/toggle-group.tsx)
- [src/components/ui/toggle.tsx](../src/components/ui/toggle.tsx)
- [src/components/ui/tooltip.tsx](../src/components/ui/tooltip.tsx)
- [src/components/ui/use-mobile.ts](../src/components/ui/use-mobile.ts)
- [src/components/ui/utils.ts](../src/components/ui/utils.ts)
- [src/index.css](../src/index.css)
- [src/lib/AuthContext.tsx](../src/lib/AuthContext.tsx)
- [src/lib/api.ts](../src/lib/api.ts)
- [src/main.tsx](../src/main.tsx)
- [src/pages/AdminDashboard.tsx](../src/pages/AdminDashboard.tsx)
- [src/pages/AgriculturePension.tsx](../src/pages/AgriculturePension.tsx)
- [src/pages/DisabilityPension.tsx](../src/pages/DisabilityPension.tsx)
- [src/pages/Home.tsx](../src/pages/Home.tsx)
- [src/pages/Login.tsx](../src/pages/Login.tsx)
- [src/pages/MyIssues.tsx](../src/pages/MyIssues.tsx)
- [src/pages/NotFound.tsx](../src/pages/NotFound.tsx)
- [src/pages/NoticeBoard.tsx](../src/pages/NoticeBoard.tsx)
- [src/pages/OldAgePension.tsx](../src/pages/OldAgePension.tsx)
- [src/pages/PostIssue.tsx](../src/pages/PostIssue.tsx)
- [src/pages/Register.tsx](../src/pages/Register.tsx)
- [src/pages/Snehasparsham.tsx](../src/pages/Snehasparsham.tsx)
- [src/pages/StrayDogReport.tsx](../src/pages/StrayDogReport.tsx)
- [src/pages/UnmarriedWomenPension.tsx](../src/pages/UnmarriedWomenPension.tsx)
- [src/pages/Vayomithram.tsx](../src/pages/Vayomithram.tsx)
- [src/pages/WidowPension.tsx](../src/pages/WidowPension.tsx)
- [src/styles/globals.css](../src/styles/globals.css)
- [tailwind.config.js](../tailwind.config.js)
- [tsconfig.json](../tsconfig.json)
- [tsconfig.node.json](../tsconfig.node.json)
- [vite.config.ts](../vite.config.ts)
