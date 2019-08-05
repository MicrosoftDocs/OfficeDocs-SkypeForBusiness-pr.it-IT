---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute è una tabella hardcoded che contiene gli attributi Visibility e Behavior usati nella tabella Node.
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194685"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute è una tabella hardcoded che contiene gli attributi Visibility e Behavior usati nella tabella Node.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint e non null  <br/> |ID dell'attributo.  <br/> |
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
