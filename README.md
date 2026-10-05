<!-- ****************************Prompt********************************* -->

i want to make project called "job tracker" which would useful for me 
and also can be mentioned in my resume as i'm 2.8 years experienced 
frontend focused developer with some backend exposure node js personal 
and some flask rest api and postgresql so i want make thhis project 
using react.js, node.js, postgresql, authentication, search/filtering 
and scheduled notification

┌──────────────────────────────────────────────────────────────┐
│ JobTracker                         🔔  👤 Profile            │
├──────────────┬───────────────────────────────────────────────┤
│              │                                               │
│ Dashboard    │  Good morning!                               │
│ Applications│                                               │
│ Interviews   │  ┌────────┐ ┌────────┐ ┌────────┐ ┌────────┐│
│ Companies    │  │ 42     │ │ 18     │ │ 7      │ │ 3      ││
│ Reminders    │  │Applied │ │Active  │ │Interview│ │Offers ││
│              │  └────────┘ └────────┘ └────────┘ └────────┘│
│              │                                               │
│              │  Application Pipeline                         │
│              │                                               │
│              │ Applied → Screening → Interview → Offer       │
│              │                                               │
│              │  Upcoming Follow-ups                          │
│              │  ─────────────────────────────────────────    │
│              │  Google · Frontend Engineer · Tomorrow        │
│              │  Razorpay · React Developer · Oct 8            │
│              │                                               │
└──────────────┴───────────────────────────────────────────────┘


                    ┌──────────────────────┐
                    │      React + TS      │
                    │                      │
                    │ Dashboard            │
                    │ Applications         │
                    │ Interviews           │
                    │ Notifications        │
                    └──────────┬───────────┘
                               │
                         REST API / HTTPS
                               │
                               ▼
                    ┌──────────────────────┐
                    │    Node + Express    │
                    │                      │
                    │ Auth                 │
                    │ Applications         │
                    │ Interviews           │
                    │ Notifications        │
                    └───────┬───────┬──────┘
                            │       │
                            ▼       ▼
                     ┌──────────┐ ┌──────────┐
                     │PostgreSQL│ │  Redis   │
                     └──────────┘ └────┬─────┘
                                       │
                                       ▼
                                  ┌──────────┐
                                  │ BullMQ   │
                                  │ Worker   │
                                  └────┬─────┘
                                       │
                                       ▼
                                Email / Alerts

<!-- ********************Recommended-Stack******************** -->

Layer	Technology
Frontend	React.js + TypeScript
Styling	Tailwind CSS
State	React Query + Context/Zustand
Backend	Node.js + Express.js
API	REST API
Database	PostgreSQL
ORM	Prisma
Authentication	JWT + refresh tokens
Validation	Zod
Notifications	Node.js worker + BullMQ
Queue	Redis
Email	Resend / Nodemailer
Deployment	Vercel + Render/Railway/Fly.io
Testing	Vitest + React Testing Library + Jest/Supertest
API documentation	Swagger/OpenAPI
Version control	Git + GitHub


Job Tracker — Full-Stack Job Application Management Platform

Built a full-stack job application tracking platform using React, TypeScript, Node.js, Express, PostgreSQL, and Prisma, enabling users to manage applications, companies, interview rounds, notes, reminders, and resume versions.

Implemented JWT-based authentication with access/refresh tokens, HTTP-only cookies, protected API routes, request validation, and authorization to secure user data.

Developed server-side search, multi-criteria filtering, sorting, and pagination for efficiently managing large numbers of job applications.

Built a background notification system using Redis and BullMQ to schedule follow-up reminders and interview notifications, with support for in-app and email notifications.

Created a responsive analytics dashboard displaying application funnels, response rates, application sources, upcoming interviews, and follow-up activities.

Added automated tests, API documentation, Docker-based local development, structured error handling, and CI/CD for production-oriented development.


<!-- ***********************Frontend-Architecture************************* -->

frontend/
│
├── public/
│   ├── favicon.svg
│   └── logo.svg
│
├── src/
│   │
│   ├── app/
│   │   ├── App.tsx
│   │   ├── router.tsx
│   │   ├── providers.tsx
│   │   └── query-client.ts
│   │
│   ├── assets/
│   │   ├── images/
│   │   └── icons/
│   │
│   ├── components/
│   │   ├── ui/
│   │   │   ├── Button.tsx
│   │   │   ├── Input.tsx
│   │   │   ├── Select.tsx
│   │   │   ├── Textarea.tsx
│   │   │   ├── Modal.tsx
│   │   │   ├── Dialog.tsx
│   │   │   ├── Dropdown.tsx
│   │   │   ├── Badge.tsx
│   │   │   ├── Avatar.tsx
│   │   │   ├── Spinner.tsx
│   │   │   ├── Skeleton.tsx
│   │   │   ├── EmptyState.tsx
│   │   │   ├── ErrorState.tsx
│   │   │   ├── Pagination.tsx
│   │   │   └── Tooltip.tsx
│   │   │
│   │   ├── layout/
│   │   │   ├── AppLayout.tsx
│   │   │   ├── Sidebar.tsx
│   │   │   ├── Header.tsx
│   │   │   ├── MobileNavigation.tsx
│   │   │   └── PageContainer.tsx
│   │   │
│   │   └── common/
│   │       ├── ConfirmDialog.tsx
│   │       ├── SearchInput.tsx
│   │       ├── DatePicker.tsx
│   │       ├── StatusBadge.tsx
│   │       └── ErrorBoundary.tsx
│   │
│   ├── features/
│   │   │
│   │   ├── auth/
│   │   │   ├── api/
│   │   │   │   └── auth.api.ts
│   │   │   ├── components/
│   │   │   │   ├── LoginForm.tsx
│   │   │   │   ├── RegisterForm.tsx
│   │   │   │   └── ProtectedRoute.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useLogin.ts
│   │   │   │   ├── useRegister.ts
│   │   │   │   └── useCurrentUser.ts
│   │   │   ├── schemas/
│   │   │   │   └── auth.schema.ts
│   │   │   ├── types/
│   │   │   │   └── auth.types.ts
│   │   │   └── store/
│   │   │       └── auth.store.ts
│   │   │
│   │   ├── applications/
│   │   │   ├── api/
│   │   │   │   └── applications.api.ts
│   │   │   ├── components/
│   │   │   │   ├── ApplicationCard.tsx
│   │   │   │   ├── ApplicationTable.tsx
│   │   │   │   ├── ApplicationForm.tsx
│   │   │   │   ├── ApplicationDetails.tsx
│   │   │   │   ├── ApplicationStatus.tsx
│   │   │   │   ├── ApplicationFilters.tsx
│   │   │   │   ├── ApplicationSearch.tsx
│   │   │   │   ├── ApplicationSort.tsx
│   │   │   │   ├── ApplicationTimeline.tsx
│   │   │   │   └── ApplicationPipeline.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useApplications.ts
│   │   │   │   ├── useApplication.ts
│   │   │   │   ├── useCreateApplication.ts
│   │   │   │   ├── useUpdateApplication.ts
│   │   │   │   ├── useDeleteApplication.ts
│   │   │   │   └── useUpdateApplicationStatus.ts
│   │   │   ├── schemas/
│   │   │   │   └── application.schema.ts
│   │   │   ├── types/
│   │   │   │   └── application.types.ts
│   │   │   └── utils/
│   │   │       └── application.utils.ts
│   │   │
│   │   ├── companies/
│   │   │   ├── api/
│   │   │   │   └── companies.api.ts
│   │   │   ├── components/
│   │   │   │   ├── CompanyForm.tsx
│   │   │   │   ├── CompanyCard.tsx
│   │   │   │   └── CompanySelector.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useCompanies.ts
│   │   │   │   └── useCompany.ts
│   │   │   ├── schemas/
│   │   │   │   └── company.schema.ts
│   │   │   └── types/
│   │   │       └── company.types.ts
│   │   │
│   │   ├── interviews/
│   │   │   ├── api/
│   │   │   │   └── interviews.api.ts
│   │   │   ├── components/
│   │   │   │   ├── InterviewForm.tsx
│   │   │   │   ├── InterviewCard.tsx
│   │   │   │   ├── InterviewList.tsx
│   │   │   │   └── InterviewTimeline.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useInterviews.ts
│   │   │   │   ├── useCreateInterview.ts
│   │   │   │   └── useUpdateInterview.ts
│   │   │   ├── schemas/
│   │   │   │   └── interview.schema.ts
│   │   │   └── types/
│   │   │       └── interview.types.ts
│   │   │
│   │   ├── notes/
│   │   │   ├── api/
│   │   │   │   └── notes.api.ts
│   │   │   ├── components/
│   │   │   │   ├── NoteForm.tsx
│   │   │   │   ├── NoteCard.tsx
│   │   │   │   └── NotesList.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useNotes.ts
│   │   │   │   ├── useCreateNote.ts
│   │   │   │   └── useDeleteNote.ts
│   │   │   └── types/
│   │   │       └── note.types.ts
│   │   │
│   │   ├── reminders/
│   │   │   ├── api/
│   │   │   │   └── reminders.api.ts
│   │   │   ├── components/
│   │   │   │   ├── ReminderForm.tsx
│   │   │   │   ├── ReminderCard.tsx
│   │   │   │   └── ReminderList.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useReminders.ts
│   │   │   │   ├── useCreateReminder.ts
│   │   │   │   └── useDeleteReminder.ts
│   │   │   ├── schemas/
│   │   │   │   └── reminder.schema.ts
│   │   │   └── types/
│   │   │       └── reminder.types.ts
│   │   │
│   │   ├── notifications/
│   │   │   ├── api/
│   │   │   │   └── notifications.api.ts
│   │   │   ├── components/
│   │   │   │   ├── NotificationBell.tsx
│   │   │   │   ├── NotificationDropdown.tsx
│   │   │   │   ├── NotificationItem.tsx
│   │   │   │   └── NotificationList.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useNotifications.ts
│   │   │   │   └── useMarkNotificationRead.ts
│   │   │   └── types/
│   │   │       └── notification.types.ts
│   │   │
│   │   ├── resumes/
│   │   │   ├── api/
│   │   │   │   └── resumes.api.ts
│   │   │   ├── components/
│   │   │   │   ├── ResumeUpload.tsx
│   │   │   │   ├── ResumeCard.tsx
│   │   │   │   └── ResumeList.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useResumes.ts
│   │   │   │   ├── useUploadResume.ts
│   │   │   │   └── useDeleteResume.ts
│   │   │   └── types/
│   │   │       └── resume.types.ts
│   │   │
│   │   └── dashboard/
│   │       ├── api/
│   │       │   └── dashboard.api.ts
│   │       ├── components/
│   │       │   ├── StatsCards.tsx
│   │       │   ├── ApplicationFunnel.tsx
│   │       │   ├── ApplicationsBySource.tsx
│   │       │   ├── ResponseRate.tsx
│   │       │   ├── RecentApplications.tsx
│   │       │   ├── UpcomingInterviews.tsx
│   │       │   └── UpcomingReminders.tsx
│   │       ├── hooks/
│   │       │   └── useDashboardStats.ts
│   │       └── types/
│   │           └── dashboard.types.ts
│   │
│   ├── pages/
│   │   ├── auth/
│   │   │   ├── LoginPage.tsx
│   │   │   └── RegisterPage.tsx
│   │   │
│   │   ├── dashboard/
│   │   │   └── DashboardPage.tsx
│   │   │
│   │   ├── applications/
│   │   │   ├── ApplicationsPage.tsx
│   │   │   ├── CreateApplicationPage.tsx
│   │   │   └── ApplicationDetailsPage.tsx
│   │   │
│   │   ├── interviews/
│   │   │   └── InterviewsPage.tsx
│   │   │
│   │   ├── reminders/
│   │   │   └── RemindersPage.tsx
│   │   │
│   │   ├── notifications/
│   │   │   └── NotificationsPage.tsx
│   │   │
│   │   ├── resumes/
│   │   │   └── ResumesPage.tsx
│   │   │
│   │   ├── companies/
│   │   │   └── CompaniesPage.tsx
│   │   │
│   │   └── settings/
│   │       ├── ProfilePage.tsx
│   │       └── SecurityPage.tsx
│   │
│   ├── hooks/
│   │   ├── useDebounce.ts
│   │   ├── useMediaQuery.ts
│   │   └── usePagination.ts
│   │
│   ├── lib/
│   │   ├── axios.ts
│   │   ├── query-client.ts
│   │   └── utils.ts
│   │
│   ├── types/
│   │   ├── api.types.ts
│   │   └── common.types.ts
│   │
│   ├── constants/
│   │   ├── application-status.ts
│   │   ├── work-mode.ts
│   │   └── routes.ts
│   │
│   ├── styles/
│   │   └── globals.css
│   │
│   ├── main.tsx
│   └── vite-env.d.ts
│
├── .env
├── .env.example
├── eslint.config.js
├── prettier.config.js
├── tsconfig.json
├── vite.config.ts
├── package.json
└── README.md

<!-- ***********************Backend-Architecture************************* -->

backend/
│
├── src/
│   │
│   ├── config/
│   │   ├── env.ts
│   │   ├── database.ts
│   │   └── redis.ts
│   │
│   ├── controllers/
│   │   ├── auth.controller.ts
│   │   ├── application.controller.ts
│   │   ├── company.controller.ts
│   │   ├── interview.controller.ts
│   │   ├── note.controller.ts
│   │   ├── reminder.controller.ts
│   │   ├── notification.controller.ts
│   │   ├── resume.controller.ts
│   │   └── dashboard.controller.ts
│   │
│   ├── services/
│   │   ├── auth.service.ts
│   │   ├── application.service.ts
│   │   ├── company.service.ts
│   │   ├── interview.service.ts
│   │   ├── note.service.ts
│   │   ├── reminder.service.ts
│   │   ├── notification.service.ts
│   │   ├── resume.service.ts
│   │   ├── dashboard.service.ts
│   │   └── email.service.ts
│   │
│   ├── repositories/
│   │   ├── user.repository.ts
│   │   ├── application.repository.ts
│   │   ├── company.repository.ts
│   │   ├── interview.repository.ts
│   │   ├── note.repository.ts
│   │   ├── reminder.repository.ts
│   │   ├── notification.repository.ts
│   │   └── resume.repository.ts
│   │
│   ├── routes/
│   │   ├── index.ts
│   │   ├── auth.routes.ts
│   │   ├── application.routes.ts
│   │   ├── company.routes.ts
│   │   ├── interview.routes.ts
│   │   ├── note.routes.ts
│   │   ├── reminder.routes.ts
│   │   ├── notification.routes.ts
│   │   ├── resume.routes.ts
│   │   └── dashboard.routes.ts
│   │
│   ├── middleware/
│   │   ├── auth.middleware.ts
│   │   ├── error.middleware.ts
│   │   ├── rate-limit.middleware.ts
│   │   ├── validate.middleware.ts
│   │   └── not-found.middleware.ts
│   │
│   ├── validators/
│   │   ├── auth.validator.ts
│   │   ├── application.validator.ts
│   │   ├── company.validator.ts
│   │   ├── interview.validator.ts
│   │   ├── note.validator.ts
│   │   ├── reminder.validator.ts
│   │   └── resume.validator.ts
│   │
│   ├── jobs/
│   │   ├── reminder.job.ts
│   │   ├── interview-reminder.job.ts
│   │   └── follow-up-reminder.job.ts
│   │
│   ├── workers/
│   │   ├── notification.worker.ts
│   │   └── email.worker.ts
│   │
│   ├── queues/
│   │   ├── notification.queue.ts
│   │   └── email.queue.ts
│   │
│   ├── utils/
│   │   ├── jwt.ts
│   │   ├── password.ts
│   │   ├── pagination.ts
│   │   ├── date.ts
│   │   └── logger.ts
│   │
│   ├── types/
│   │   ├── express.d.ts
│   │   ├── auth.types.ts
│   │   ├── application.types.ts
│   │   └── common.types.ts
│   │
│   ├── constants/
│   │   ├── application-status.ts
│   │   ├── notification-type.ts
│   │   └── error-code.ts
│   │
│   ├── app.ts
│   └── server.ts
│
├── prisma/
│   ├── schema.prisma
│   ├── seed.ts
│   │
│   └── migrations/
│       ├── ...
│       └── migration_lock.toml
│
├── tests/
│   ├── integration/
│   │   ├── auth.test.ts
│   │   ├── applications.test.ts
│   │   ├── interviews.test.ts
│   │   └── reminders.test.ts
│   │
│   └── unit/
│       ├── auth.service.test.ts
│       ├── application.service.test.ts
│       └── reminder.service.test.ts
│
├── .env
├── .env.example
├── eslint.config.js
├── prettier.config.js
├── tsconfig.json
├── package.json
└── README.md


