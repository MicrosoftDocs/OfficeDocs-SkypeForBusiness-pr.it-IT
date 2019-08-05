---
title: tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contiene l'albero di oggetti (con nodi Category o chat room) come gestito nel pannello di controllo e nei cmdlet amministrativi.
ms.openlocfilehash: fedb7f88cd9b5a634fe9a6b34f746e61e6ee9be7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194676"
---
# <a name="tblnode"></a>tblNode
 
tblNode contiene l'albero di oggetti (con nodi Category o chat room) come gestito nel pannello di controllo e nei cmdlet amministrativi.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, not null  <br/> |ID nodo (numero univoco).  <br/> |
|nodeGuid  <br/> |GUID, non null  <br/> |GUID del nodo.  <br/> |
|parentID  <br/> |int  <br/> |ID nodo dell'elemento padre. Il nodo radice (con ID 1) si include anche come padre.  <br/> |
|nodeType  <br/> |bit, not null  <br/> |True se il nodo è una categoria.  <br/> False se il nodo è una chat room.  <br/> |
|nodeName  <br/> |nvarchar (256), not null  <br/> |Nome del nodo.  <br/> |
|nodeDesc  <br/> |nvarchar (256), not null  <br/> |Descrizione del nodo.  <br/> |
|invitare  <br/> |po'  <br/> | Per le categorie: <br/>  True se gli inviti sono attivati. <br/>  False se gli inviti sono spenti. <br/>  Per le camere: <br/>  False se gli inviti sono disattivati (esegue l'override della categoria padre). <br/>  Null se l'impostazione invita viene ereditata dalla categoria padre. <br/> |
|connessi  <br/> |po'  <br/> | Per le categorie: <br/>  True se la cronologia chat è attivata. <br/>  False se la cronologia chat è disinserita. <br/>  Per le camere: <br/>  Null. <br/> |
|filePost  <br/> |po'  <br/> | Per le categorie: <br/>  True se gli upload di file sono consentiti. <br/>  False se gli upload di file non sono consentiti. <br/>  Per le camere: <br/>  Null. <br/> |
|disabilitato  <br/> |bit, not null  <br/> |True se la chat room è disabilitata. Si applica solo alle chat room. (False per le categorie)  <br/> |
|comportamento  <br/> |smallint e non null  <br/> | Comportamento (ricercato nella tabella EnumValue): <br/>  4: normale (normale chat room). <br/>  5: Auditorium (auditorium chat room, solo i relatori possono collaborare). <br/>  Si applica solo alle chat room. <br/> |
|visibilità  <br/> |smallint e non null  <br/> | Visibilità (ricercata nella tabella EnumValue): <br/>  2: privato <br/>  3: ambito <br/>  6: aprire <br/>  Si applica solo alle chat room. <br/> |
|siopID  <br/> |GUID  <br/> |GUID del componente aggiuntivo se un componente aggiuntivo è associato a questa chat room. (Le categorie non hanno componenti aggiuntivi)  <br/> Le informazioni del componente aggiuntivo sono ricercate nella tabella SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, not null  <br/> |ID dell'entità che ha creato questo nodo.  <br/> |
|nodeAddedOn  <br/> |bigint e non null  <br/> |Indicatore di data e ora della creazione di nodi.  <br/> |
|nodeUpdatedBy  <br/> |int, not null  <br/> |ID dell'entità che ha eseguito l'aggiornamento più recente di questo nodo.  <br/> |
|nodeUpdatedOn  <br/> |bigint e non null  <br/> |Indicatore di data e ora dell'ultimo aggiornamento di questo nodo.  <br/> |
|purgedOn  <br/> |DateTime  <br/> |Ora dell'ultima operazione di eliminazione dei ripulimenti (rimozione degli ambiti da tabella tblScopedPrincipal e ruoli della tabella tblPrincipalRole) che hanno interessato questo nodo. Viene usato dal meccanismo di aggiornamento della cache interno del servizio chat.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|nodeID  <br/> |Chiave primaria.  <br/> |
|comportamento  <br/> |Chiave esterna con ricerca nella tabella tblEnumValue. valueID.  <br/> |
|visibilità  <br/> |Chiave esterna con ricerca nella tabella tblEnumValue. valueID.  <br/> |
|parentID  <br/> |Chiave esterna con ricerca nella tabella tblNode. nodeID.  <br/> |
|siopID  <br/> |Chiave esterna con ricerca nella tabella tblSiopWhiteList. siopId.  <br/> |
   

