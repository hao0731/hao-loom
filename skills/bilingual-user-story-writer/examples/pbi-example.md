# Story Title
Add browser tab unread message badge support

## Background

**中文：**  
目前聊天系統缺少在瀏覽器分頁層級提示未讀訊息的能力，導致使用者在切換到其他分頁時，較難即時注意到新訊息。為了提升通知可見性，需要補上瀏覽器分頁標題的未讀提示能力，作為現有通知機制的補充。

**English:**  
The current chat system does not provide unread message visibility at the browser tab level, making it harder for users to notice new messages while viewing other tabs. To improve notification visibility, the system needs support for unread indicators in the browser tab title as a complement to the existing notification mechanisms.

## Description

**中文：**  
此 PBI 主要描述系統層級需要新增的能力：根據未讀訊息狀態動態更新瀏覽器分頁標題，並在未讀數清空後恢復預設標題。此項目聚焦於功能行為與狀態更新規則，不限定具體前端技術實作方式。

**English:**  
This PBI describes a system-level capability that needs to be added: dynamically updating the browser tab title based on unread message status and restoring the default title once the unread count is cleared. This item focuses on behavior and state update rules rather than mandating a specific frontend implementation approach.

## Requirements

**中文：**  
- 系統需支援根據未讀訊息狀態動態更新瀏覽器分頁標題。  
- 系統需支援在分頁標題中呈現未讀訊息數量。  
- 系統需支援在未讀訊息數量歸零時恢復預設標題。  
- 系統需確保未讀數變化時，分頁標題同步更新。  
- 系統需確保此能力可套用於既有聊天頁面流程。

**English:**  
- The system must support dynamically updating the browser tab title based on unread message status.  
- The system must support displaying the unread message count in the tab title.  
- The system must support restoring the default tab title when the unread count returns to zero.  
- The system must ensure the tab title stays synchronized with unread count changes.  
- The system must ensure this capability can be applied to the existing chat page flow.

## Acceptance Criteria

**中文（使用 Given / When / Then）：**  
- Given 聊天頁面已載入且系統可取得未讀訊息數量  
  When 未讀訊息數量大於 0  
  Then 瀏覽器分頁標題應顯示未讀數提示

- Given 瀏覽器分頁標題目前顯示未讀數提示  
  When 未讀訊息數量更新  
  Then 分頁標題應同步反映最新未讀數

- Given 瀏覽器分頁標題目前顯示未讀數提示  
  When 未讀訊息數量變為 0  
  Then 分頁標題應恢復為預設標題

**English (using Given / When / Then):**  
- Given the chat page is loaded and the system can access the unread message count  
  When the unread message count is greater than 0  
  Then the browser tab title should display an unread count indicator

- Given the browser tab title is currently showing an unread count indicator  
  When the unread message count changes  
  Then the tab title should reflect the latest unread count

- Given the browser tab title is currently showing an unread count indicator  
  When the unread message count becomes 0  
  Then the tab title should return to the default title