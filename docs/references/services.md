---
layout: default
title: uSupport.Services
parent: References
nav_order: 2
---

## IuSupportTicketService
```c#
IEnumerable<uSupportTicket> GetAll();
uSupportPage<uSupportTicket> GetPagedResolvedTickets(long page, string? searchTerm = null, uSupportSort? sort = null);
uSupportPage<uSupportTicket> GetPagedActiveTickets(long page, string? searchTerm = null, uSupportSort? sort = null);
bool AnyResolvedTickets();
uSupportTicket Get(Guid id);
uSupportTicket Create(uSupportTicketSchema ticket);
uSupportTicket Update(uSupportTicketSchema ticketDto);
void Delete(Guid id);
```

## IuSupportTicketTypeService
```c#
IEnumerable<uSupportTicketType> GetAll();
uSupportTicketType Get(Guid id);
IEnumerable<uSupportTicketType> GetByIds(List<Guid> ids);
Guid? GetTypeIdFromName(string name);
uSupportTicketType Create(uSupportTicketTypeSchema ticketType);
uSupportTicketType Update(uSupportTicketTypeSchema ticketType);
void Delete(Guid id);
int GetTypesCount();
```

## IuSupportTicketStatusService
```c#
IEnumerable<uSupportTicketStatus> GetAll();
IEnumerable<uSupportTicketStatus> GetResolvedStatuses();
IEnumerable<uSupportTicketStatus> GetActiveStatuses();
uSupportTicketStatus GetDefaultStatus();
uSupportTicketStatus Get(Guid id);
IEnumerable<uSupportTicketStatus> GetByIds(List<Guid> ids);
Guid GetStatusIdFromName(string name);
uSupportTicketStatus Create(uSupportTicketStatusSchema ticketStatus);
uSupportTicketStatus Update(uSupportTicketStatusSchema ticketStatus);
void Delete(Guid id);
int GetStatusCount();
```

## IuSupportSettingsService
```c#
void SendEmail(string toAddress, string subject, string templateViewPath, object model);
uSupportSettings GetSettings();
uSupportSettings Get(Guid id);
uSupportSettings Create(uSupportSettingsSchema settings);
uSupportSettings Update(uSupportSettingsSchema settings);
void Delete(Guid id);
```

## IuSupportTicketCommentService
```c#
IEnumerable<uSupportTicketComment> GetCommentsFromTicketId(Guid ticketId);
uSupportPage<uSupportTicketComment> GetPagedCommentsForTicket(Guid ticketId, long page);
IEnumerable<uSupportTicketComment> GetAll();
uSupportTicketComment Get(Guid id);
uSupportTicketComment Create(uSupportTicketCommentSchema comment);
uSupportTicketComment Update(uSupportTicketCommentSchema comment);
void DeleteByTicketId(Guid ticketId);
void Delete(Guid id);
```

## IuSupportTicketHistoryService
```c#
IEnumerable<uSupportTicketHistory> GetByTicketId(Guid ticketId);
uSupportPage<uSupportTicketHistory> GetPagedByTicketId(Guid ticketId, long page);
uSupportTicketHistory Get(Guid id);
uSupportTicketHistory Create(uSupportTicketHistorySchema history);
uSupportTicketHistory Update(uSupportTicketHistorySchema history);
void DeleteByTicketId(Guid ticketId);
void Delete(Guid id);
```
