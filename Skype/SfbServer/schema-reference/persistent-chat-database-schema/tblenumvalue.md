---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue è una tabella hardcoded che contiene i valori di visibilità e comportamento degli attributi usati nella tabella Node.
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814604"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue è una tabella hardcoded che contiene i valori di visibilità e comportamento degli attributi usati nella tabella Node.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint e non null  <br/> |ID del valore.  <br/> |
|attributeID  <br/> |smallint e non null  <br/> |ID dell'attributo.  <br/> |
|attributeValue  <br/> |nvarchar (256), not null  <br/> |Nome del valore.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|valueID  <br/> |Chiave primaria.  <br/> |
|attributeID  <br/> |Chiave esterna con ricerca nella tabella tblEnumAttribute. attributeID.  <br/> |
   
**Valori tabella**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |privato  <br/> |
|3  <br/> |1  <br/> |ambito  <br/> |
|4  <br/> |2  <br/> |normale  <br/> |
|5  <br/> |2  <br/> |Auditorium  <br/> |
|6  <br/> |1  <br/> |aprire  <br/> |
   
## <a name="see-also"></a>Vedere anche

[tblNode](tblnode.md)
