---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute è una tabella hardcoded in cui sono inclusi gli attributi Visibility e Behavior utilizzati nella tabella Node.
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809716"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute è una tabella hardcoded in cui sono inclusi gli attributi Visibility e Behavior utilizzati nella tabella Node.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, not null  <br/> |ID dell'attributo.  <br/> |
|attributeName  <br/> |nvarchar (256), not null  <br/> |Nome dell'attributo.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|attributeID  <br/> |Chiave primaria.  <br/> |
   
**Valori tabella**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1   <br/> |Visibilità.  <br/> |
|2   <br/> |Comportamento.  <br/> |
   
## <a name="see-also"></a>Vedere anche

[tblNode](tblnode.md)
