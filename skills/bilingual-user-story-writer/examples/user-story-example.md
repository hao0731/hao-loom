# Story Title
As a member, I want to see the unread message count on the browser tab, so that I can notice new messages even when I am viewing another tab.

## Background

**中文：**  
目前使用者在聊天室收到新訊息時，如果剛好切換到其他瀏覽器分頁，容易忽略新訊息。團隊希望透過瀏覽器分頁標題顯示未讀數，讓使用者即使不在目前聊天室畫面，也能快速察覺有新訊息進來。

**English:**  
Currently, when users receive new messages in the chat system while viewing another browser tab, they may easily miss those messages. The team wants to show the unread message count in the browser tab title so users can quickly notice incoming messages even when they are not actively viewing the chat page.

## Description

**中文：**  
系統需要在使用者有未讀訊息時，更新瀏覽器分頁標題，例如在原本的頁面標題前方加上未讀數。當使用者返回聊天室並讀取訊息後，分頁標題應恢復為原本的標題文字。此功能應以不干擾既有聊天流程為前提，並正確反映未讀狀態。

**English:**  
The system should update the browser tab title when the user has unread messages, for example by adding the unread count before the original page title. When the user returns to the chat and the messages are read, the tab title should revert to the original title. This feature should work without disrupting the existing chat flow and should accurately reflect the unread state.

## Requirements

**中文：**  
- 當使用者有未讀訊息時，系統必須在瀏覽器分頁標題中顯示未讀數。  
- 未讀數應反映目前尚未讀取的新訊息數量。  
- 當所有訊息已被讀取後，瀏覽器分頁標題應恢復為預設標題。  
- 當新的未讀訊息持續進來時，未讀數應即時更新。  
- 此功能不得影響使用者正常收發訊息的流程。

**English:**  
- When the user has unread messages, the system must display the unread count in the browser tab title.  
- The unread count should reflect the number of new messages that have not yet been read.  
- When all messages have been read, the browser tab title should return to the default title.  
- When additional unread messages arrive, the unread count should be updated in near real time.  
- This feature must not interrupt the user’s normal messaging flow.

## Acceptance Criteria

**中文（使用 Given / When / Then）：**  
- Given 使用者已登入聊天室，且目前切換到其他瀏覽器分頁  
  When 有一則新訊息送達  
  Then 瀏覽器分頁標題應顯示未讀數與原始標題

- Given 使用者已有 3 則未讀訊息  
  When 又收到 2 則新訊息  
  Then 瀏覽器分頁標題中的未讀數應更新為 5

- Given 使用者有未讀訊息，且分頁標題已顯示未讀數  
  When 使用者返回聊天室並將訊息標記為已讀  
  Then 瀏覽器分頁標題應恢復為原始標題

**English (using Given / When / Then):**  
- Given the user is logged into the chat system and is currently viewing another browser tab  
  When a new message arrives  
  Then the browser tab title should display the unread count together with the original title

- Given the user already has 3 unread messages  
  When 2 more new messages arrive  
  Then the unread count in the browser tab title should be updated to 5

- Given the user has unread messages and the tab title is already showing the unread count  
  When the user returns to the chat and marks the messages as read  
  Then the browser tab title should return to the original title