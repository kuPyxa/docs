# Управление рабочими процессами

Рабочий процесс задает допустимые статусы задач и их последовательность. Управлять рабочими процессами в очереди может ее владелец и пользователи, которым он выдал [доступ к настройкам очереди](queue-access.md).

Как можно управлять рабочими процессами:

* добавить [типы задач](./add-ticket-type.md) в существующие рабочие процессы и создать новые типы задач;
* [настроить резолюции](./create-resolution.md) для разных типов задач;
* редактировать и удалять рабочие процессы, не забывая о поддержке [совместимости](./backward-compatibility.md) с существующими задачами очереди;
* копировать рабочие процессы;
* перейти в редактор рабочих процессов, в котором можно [создать рабочий процесс](#create-workflow), добавить в него [статусы](./workflow-status-edit.md) и [настроить переходы](./workflow-action-edit.md) между ними.

## Правила нового рабочего процесса {#rules}

1. Минимальный состав рабочего процесса: 2 статуса и переход между ними.

1. В рабочем процессе не должно быть статусов без переходов.

1. Один из статусов должен быть [началом рабочего процесса](./workflow-status-edit.md#initial-status). Началом рабочего процесса может быть статус любого типа.

1. Как минимум один из статусов должен быть [типа](./workflow-status-edit.md#status-types) «Завершен» или «Отменен» — без него в вашей очереди не получится закрывать задачи.

## Создать рабочий процесс {#create}

Чтобы создать рабочий процесс:

1. Перейдите на страницу очереди.

1. В верхнем правом углу нажмите ![](../../_assets/tracker/svg/settings-old.svg) **{{ ui-key.startrek.ui_Queues_pages_PageQueue_header.settings }}**.

1. Перейдите на вкладку **{{ ui-key.startrek.ui_Queues_pages_page-queue-admin_QueueAdminPageContent.menu-item-workflows }}** и нажмите **{{ ui-key.startrek.ui_Queues_pages_queue-admin-tab-workflows_WorkflowsStateList.action-new-process }}**. Откроется визуальный редактор рабочих процессов.

1. [Добавляйте на схему статусы](./workflow-status-edit.md#add-status) и [настраивайте переходы](./workflow-action-edit.md#add-action) между ними. Придерживайтесь [правил](#rules).

## Копировать процесс из другой очереди {#copy}

Чтобы скопировать процесс из другой очереди:

1. Перейдите на страницу очереди, в которую нужно скопировать процесс.
1. В верхнем правом углу нажмите ![](../../_assets/tracker/svg/settings-old.svg) **{{ ui-key.startrek.ui_Queues_pages_PageQueue_header.settings }}**.
1. На вкладке **{{ ui-key.startrek.ui_Queues_pages_page-queue-admin_QueueAdminPageContent.menu-item-workflows }}** нажмите ![](../../_assets/tracker/svg/copy-process.svg).
1. В открывшемся окне заполните поля:
   * **{{ ui-key.startrek.ui_Queues_pages_queue-admin-tab-workflows_CopyWorkflowDialog.label-queue }}**.
   * **{{ ui-key.startrek.ui_Queues_pages_queue-admin-tab-workflows_CopyWorkflowDialog.label-workflow }}**. 
   * **{{ ui-key.startrek.ui_Queues_pages_queue-admin-tab-workflows_CopyWorkflowDialog.label-name }}**.
1. Нажмите **{{ ui-key.startrek.ui_Queues_pages_queue-admin-tab-workflows_CopyWorkflowDialog.action-copy }}**.

## Удалить рабочий процесс {#section_s35_xz5_vbb}

{% note warning %}

Невозможно удалить рабочий процесс, который действует хотя бы для одной задачи в очереди. Перед удалением рабочего процесса рекомендуем перенести его [типы задач в другой процесс](backward-compatibility.md).

{% endnote %}

Чтобы удалить рабочий процесс:

1. Откройте страницу очереди.

1. В верхнем правом углу нажмите ![](../../_assets/tracker/svg/settings-old.svg) **{{ ui-key.startrek.ui_Queues_pages_PageQueue_header.settings }}**.

1. Перейдите на вкладку **{{ ui-key.startrek.ui_Queues_pages_page-queue-admin_QueueAdminPageContent.menu-item-workflows }}**.

1. Выберите рабочий процесс и нажмите кнопку ![](../../_assets/tracker/button-delete.png).
