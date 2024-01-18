# Front-End directory
```
├── api
|  ├── addSeatChart.ts
|  ├── scs00003-list-employee.ts
|  └── update-chart.ts
├── app.vue
├── assets
|  ├── chart.svg
|  ├── css
|  ├── fonts
|  ├── icons
|  ├── images
|  ├── scss
|  └── svg
├── ci
|  ├── docker
|  ├── helm-chart
|  └── version.txt
├── components
|  ├── AppFooter.vue
|  ├── AppHeader.vue
|  ├── ChartEditor.vue
|  ├── ChartHeader.vue
|  ├── ChartSetting.vue
|  ├── DialogChartSetting.vue
|  ├── EmployeeBox.vue
|  ├── ExampleComponent.vue
|  ├── ItemBox.vue
|  ├── Loading.vue
|  ├── MemberGridItem.vue
|  ├── MessageModal.vue
|  ├── SeatCard.vue
|  ├── SeatchartCard.vue
|  ├── Sidebar.vue
|  └── UserInfo.vue
├── composables
|  ├── authState.ts
|  ├── internalState.ts
|  └── seatChartList.ts
├── constants
|  └── api.constants.ts
├── layouts
|  └── default.vue
├── libs
|  ├── chart-models.ts
|  ├── chart-utils.ts
|  ├── common-utils.ts
|  ├── consts.ts
|  ├── icons-loader.ts
|  ├── svg-utils.ts
|  └── types.d.ts
├── locales
|  ├── en.ts
|  ├── jp.ts
|  └── vi.ts
├── middleware
|  └── auth.global.ts
├── nuxt.config.ts
├── package.json
├── pages
|  ├── about.vue
|  ├── chart.vue
|  ├── index.vue
|  ├── login.vue
|  ├── member-managerment.vue
|  └── seatchart-list.vue
├── plugins
|  ├── 00.keycloak.ts
|  ├── axios.ts
|  └── emitter.ts
├── public
|  └── favicon.ico
├── README.md
├── sonar-project.properties
├── tailwind.config.js
├── tsconfig.json
└── utils
   ├── common.ts
   └── validators.ts
```
## Description
### :fontawesome-regular-folder: API
`api`Chứa các tệp TypeScript xử lý giao tiếp với API backend
### :fontawesome-regular-folder: assets
`assets`Chứa các tệp tĩnh như hình ảnh, phông chữ, tệp SVG, CSS, SCSS và icon.
### :fontawesome-regular-folder: ci
`ci`Chứa các tệp liên quan đến tích hợp liên tục (CI) và triển khai liên tục (CD), bao gồm Dockerfile, Chart Helm, và version.txt.
### :fontawesome-regular-folder: components
`components`Chứa các thành phần Vue có thể tái sử dụng
### :fontawesome-regular-folder: composables
`composables`Chứa các hàm có thể sử dụng lại trong các thành phần
### :fontawesome-regular-folder: constants
`constants`Chứa các hằng số dùng chung trong ứng dụng, bao gồm API constants 
### :fontawesome-regular-folder: layouts
`layouts`Chứa các layout chung cho các trang khác nhau, hiện có layout mặc định (default.vue).
### :fontawesome-regular-folder: libs
`libs`Chứa các thư viện riêng của dự án
### :fontawesome-regular-folder: locales
`locales`Chứa các tệp bản dịch(Anh,Nhật,Việt)
### :fontawesome-regular-folder: middleware
`middleware`Chứa các middleware của Nuxt, hiện có middleware xác thực toàn cục (auth.global.ts).
### :fontawesome-regular-folder: pages
`pages`Chứa các tệp định nghĩa các trang của ứng dụng
### :fontawesome-regular-folder: plugins
`plugins`Chứa các plugin Nuxt để mở rộng chức năng của ứng dụng
### :fontawesome-regular-folder: public
`public`Chứa các tệp tĩnh sẽ được sao chép trực tiếp vào thư mục public khi ứng dụng được xây dựng
### :fontawesome-regular-folder: utils
`utils`Chứa các hàm tiện ích chung, bao gồm các hàm common và hàm kiểm tra dữ liệu (validators.ts).