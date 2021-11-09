---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute è una tabella hardcoded in cui sono inclusi gli attributi Visibility e Behavior utilizzati nella tabella Node.
ms.openlocfilehash: a2d2fa1eacac79784e20f137a037d672fa9eaa87
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856443"
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
|1  <br/> |Visibilità.  <br/> |
|2  <br/> |Comportamento.  <br/> |
   
## <a name="see-also"></a>Vedere anche

[tblNode](tblnode.md)
