---
title: tblNode
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contiene l'albero degli oggetti (con nodi categoria o chat room) come gestito nei cmdlet del pannello di controllo e di amministrazione.
ms.openlocfilehash: cd2353d768ef61787b81efcdfe35f9c57409cc12
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815926"
---
# <a name="tblnode"></a>tblNode
 
tblNode contiene l'albero degli oggetti (con nodi categoria o chat room) come gestito nei cmdlet del pannello di controllo e di amministrazione.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, not null  <br/> |ID nodo (numero univoco).  <br/> |
|nodeGuid  <br/> |GUID, not null  <br/> |GUID nodo.  <br/> |
|parentID  <br/> |int  <br/> |ID nodo del padre. Il nodo radice (con ID 1) contiene se stesso come padre.  <br/> |
|nodeType  <br/> |bit, not null  <br/> |True se il nodo è una categoria.  <br/> False se il nodo è una chat room.  <br/> |
|nodeName  <br/> |nvarchar (256), not null  <br/> |Nome nodo.  <br/> |
|nodeDesc  <br/> |nvarchar (256), not null  <br/> |Descrizione nodo.  <br/> |
|invitare  <br/> |po'  <br/> | Per le categorie: <br/>  True se gli inviti sono attivi. <br/>  False se gli inviti sono inattivi. <br/>  Per le chat room: <br/>  False se gli inviti sono disattivati (la categoria padre viene ignorata). <br/>  Null se l'impostazione degli inviti viene ereditata dalla categoria padre. <br/> |
|registrato  <br/> |po'  <br/> | Per le categorie: <br/>  True se la cronologia della chat è attiva. <br/>  False se la cronologia della chat è inattiva. <br/>  Per le chat room: <br/>  Null. <br/> |
|filePost  <br/> |po'  <br/> | Per le categorie: <br/>  True se i caricamenti di file sono consentiti. <br/>  False se i caricamenti di file non sono consentiti. <br/>  Per le chat room: <br/>  Null. <br/> |
|disabilitati  <br/> |bit, not null  <br/> |True se la chat room è disabilitata. Si applica solo alle chat room. False per le categorie.  <br/> |
|comportamento  <br/> |smallint, not null  <br/> | Comportamento (cercato nella tabella EnumValue): <br/>  4: Normale (chat room normali) <br/>  5: Auditorium (chat room in modalità auditorium, solo i relatori possono contribuire) <br/>  Si applica solo alle chat room. <br/> |
|visibilità  <br/> |smallint, not null  <br/> | Visibilità (cercata nella tabella EnumValue): <br/>  2: Privato <br/>  3: Con ambito <br/>  6: Aperto <br/>  Si applica solo alle chat room. <br/> |
|siopID  <br/> |GUID  <br/> |GUID del componente aggiuntivo, se alla chat room è associato un componente aggiuntivo. Le categorie non hanno componenti aggiuntivi.  <br/> Le informazioni relative al componente aggiuntivo vengono cercate nella tabella SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, not null  <br/> |ID dell'entità che ha creato questo nodo.  <br/> |
|nodeAddedOn  <br/> |bigint, not null  <br/> |Indicatore di data e ora della creazione del nodo.  <br/> |
|nodeUpdatedBy  <br/> |int, not null  <br/> |ID dell'entità che ha eseguito l'ultimo aggiornamento del nodo.  <br/> |
|nodeUpdatedOn  <br/> |bigint, not null  <br/> |Indicatore di data e ora dell'ultimo aggiornamento del nodo.  <br/> |
|purgedOn  <br/> |datetime  <br/> |Ora dell'ultima operazione di eliminazione (rimozione degli ambiti dalla tabella tblScopedPrincipal e dei ruoli dalla tabella tblPrincipalRole) che ha interessato il nodo. Questo viene utilizzato dal meccanismo di aggiornamento della cache interno del servizio chat.  <br/> |
   
**Chiavi**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|nodeID  <br/> |Chiave primaria.  <br/> |
|comportamento  <br/> |Chiave esterna con ricerca nella tabella tblEnumValue.valueID.  <br/> |
|visibilità  <br/> |Chiave esterna con ricerca nella tabella tblEnumValue.valueID.  <br/> |
|parentID  <br/> |Chiave esterna con ricerca nella tabella tblNode.nodeID.  <br/> |
|siopID  <br/> |Chiave esterna con ricerca nella tabella tblSiopWhiteList.siopId.  <br/> |
   

