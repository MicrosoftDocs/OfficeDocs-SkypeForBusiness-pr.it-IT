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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute è una tabella hardcoded che contiene gli attributi Visibility e Behavior usati nella tabella Node.
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814614"
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
