---
layout: default
title: uSupport.Dtos.Tables
parent: References
nav_order: 1
---

## uSupportTypeBase
```c#
public Guid Id { get; set; }
public int Order { get; set; }
public string Alias { get; set; }
public string Name { get; set; }
public string Color { get; set; }
public string Icon { get; set; }
```


## uSupportTicket
```c#
public Guid Id { get; set; }
public string Title { get; set; }
public string Summary { get; set; }
public Guid TypeId { get; set; }
public uSupportTicketType Type { get; set; }
public Guid StatusId { get; set; }
public uSupportTicketStatus Status{ get; set; }
public int AuthorId { get; set; }

[ResultColumn]
public UserDisplay Author { get; set; }
public DateTime Submitted { get; set; }
public DateTime? Resolved { get; set; }
public string? LastUpdatedBy { get; set; }
public DateTime? LastUpdated { get; set; }
public string ExternalTicketId { get; set; }
public string PropertyValue { get; set; }
public string? InternalComment { get; set; }
public IEnumerable<uSupportTicketComment> Comments { get; set; }
```

## uSupportTicketType
```c#
public string Description { get; set; }
public int PropertyId { get; set; }
public string PropertyName { get; set; }
public string PropertyDescription { get; set; }
public string PropertyView { get; set; }

public Guid Id { get; set; }
public int Order { get; set; }
public string Alias { get; set; }
public string Name { get; set; }
public string Color { get; set; }
public string Icon { get; set; }
```

## uSupportTicketStatus
```c#
public bool Default { get; set; }
public bool Active { get; set; }

public Guid Id { get; set; }
public int Order { get; set; }
public string Alias { get; set; }
public string Name { get; set; }
public string Color { get; set; }
public string Icon { get; set; }
```

## uSupportTicketComment
```c#
public Guid Id { get; set; }
public Guid TicketId { get; set; }
public int UserId { get; set; }
public UserDisplay User { get; set; }
public DateTime Date { get; set; }
public string Comment { get; set; }
```

## uSupportTicketHistory
```c#
public Guid Id { get; set; }
public Guid TicketId { get; set; }
public string ActionType { get; set; }

[ResultColumn]
public IEnumerable<uSupportChange> Changes { get; set; }
public string ChangesJson { get; set; }
public int UserId { get; set; }

[ResultColumn]
public UserDisplay User { get; set; }
public DateTime Date { get; set; }
```
