---
title: Table Feature Row Actions
description: This document provides details about the Table Feature Row Actions component in the Components Library.
template: concept-topic-template
related:
  - title: Table Feature extension
    link: docs/marketplace/dev/front-end/page.version/table-design/table-features/index.html
  - title: Table Feature Batch Actions
    link: docs/marketplace/dev/front-end/page.version/table-design/table-features/table-feature-batch-actions.html
  - title: Table Feature Editable
    link: docs/marketplace/dev/front-end/page.version/table-design/table-features/table-feature-editable.html
  - title: Table Feature Pagination
    link: docs/marketplace/dev/front-end/page.version/table-design/table-features/table-feature-pagination.html
  - title: Table Feature Search
    link: docs/marketplace/dev/front-end/page.version/table-design/table-features/table-feature-search.html
  - title: Table Feature Selectable
    link: docs/marketplace/dev/front-end/page.version/table-design/table-features/table-feature-selectable.html
  - title: Table Feature Settings
    link: docs/marketplace/dev/front-end/page.version/table-design/table-features/table-feature-settings.html
  - title: Table Feature Sync State
    link: docs/marketplace/dev/front-end/page.version/table-design/table-features/table-feature-sync-state.html
  - title: Table Feature Title
    link: docs/marketplace/dev/front-end/page.version/table-design/table-features/table-feature-title.html
  - title: Table Feature Total
    link: docs/marketplace/dev/front-end/page.version/table-design/table-features/table-feature-total.html
---

This document explains the Table Feature Row Actions component in the Components Library.

## Overview

Table Feature Row Actions is a feature of the Table Component that renders a drop-down menu with actions applicable to the table row and when clicked triggers an Action which must be registered. Also this feature allows triggering actions via row click.
Each row has all actions by default, but they can be filtered using an array of action Ids in each row using the path configured by `availableActionsPath`.

Check out an example usage of the Table Feature Row Actions in the `@spryker/table` config.

Component configuration:

- `enabled`—enables the feature via config.  
- `actions`—an array with actions that are displayed in the drop down menu and their type of registered [action](/docs/marketplace/dev/front-end/{{page.version}}/ui-components-library/actions/).  
- `click`—indicates which action is used for clicking the table row by its `id`.
- `rowIdPath`—is used for the `rowId` action context.  
- `availableActionsPath`—path to an array with the available action IDs in the table data row (supports nested objects using dot notation for ex. `prop.nestedProp`).  

```html
<spy-table
    [config]="{
        dataSource: { ... },
        columns: [ ... ],
        rowActions: {
            enabled: true,
            actions: [
                { id: 'edit', title: 'Edit', type: 'edit-action' },
                { id: 'delete', title: 'Delete', type: 'delete-action' },
            ],
            click: 'edit',
            rowIdPath: 'sku',
            availableActionsPath: 'path.to.actions',
        },                                                                                        
    }"
>
</spy-table>
```

## Component registration

Register the component:

```ts
declare module '@spryker/table' {
    interface TableConfig {
        rowActions?: TableRowActionsConfig;
    }
}

@NgModule({
    imports: [
        TableModule.forRoot(),
        TableModule.withFeatures({
            rowActions: () =>
                import('@spryker/table.feature.row-actions').then(
                    (m) => m.TableRowActionsFeatureModule,
                ),
        }),
    ],
})
export class RootModule {}
```

```html
// Via HTML
@NgModule({
    imports: [
        TableModule.forRoot(),
        TableRowActionsFeatureModule,
    ],
})
export class RootModule {}

<spy-table [config]="config">
    <spy-table-row-actions-feature spy-table-feature></spy-table-row-actions-feature>
</spy-table>
```

## Interfaces

Below you can find interfaces for the Table Feature Row Actions:

```ts
export interface TableRowActionsConfig extends TableFeatureConfig {
    actions?: TableRowActionBase[];
    click?: string;
    rowIdPath?: string;
    availableActionsPath?: string;
}

export interface TableRowActionBase extends TableActionBase {
    title: string;
    icon?: string;
}

export interface TableRowActionContext {
    row: TableDataRow;
    rowId?: string;
}
```