---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue è una tabella hardcoded contenente i valori Visibility e Behavior degli attributi utilizzati nella tabella Node.
ms.openlocfilehash: 857c9ba916a183708ba2ff13bff2cab1ccfcea11
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863313"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue è una tabella hardcoded contenente i valori Visibility e Behavior degli attributi utilizzati nella tabella Node.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, not null  <br/> |ID del valore.  <br/> |
|attributeID  <br/> |smallint, not null  <br/> |ID dell'attributo.  <br/> |
|attributeValue  <br/> |nvarchar (256), not null  <br/> |Nome del valore.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|valueID  <br/> |Chiave primaria.  <br/> |
|attributeID  <br/> |Chiave esterna con ricerca nella tabella tblEnumAttribute.attributeID.  <br/> |
   
**Valori della tabella**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |private  <br/> |
|3   <br/> |1  <br/> |ambito  <br/> |
|4   <br/> |2  <br/> |normal  <br/> |
|5  <br/> |2  <br/> |auditorium  <br/> |
|6   <br/> |1  <br/> |open  <br/> |
   
## <a name="see-also"></a>Vedere anche

[tblNode](tblnode.md)
