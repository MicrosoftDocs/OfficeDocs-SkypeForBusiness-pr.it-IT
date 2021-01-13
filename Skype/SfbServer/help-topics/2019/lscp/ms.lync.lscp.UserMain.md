---
title: Pannello di controllo-ricerca utente aggiornata
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: NOINDEX, NOFOLLOW
description: È possibile utilizzare i risultati di una query di ricerca per configurare gli utenti di Skype for Business Server. È possibile ricercare utenti in base al nome visualizzato, al nome, al cognome, al nome dell'account SAM (Security Accounts Manager), all'indirizzo SIP o all'URI (Uniform Resource Identifier) della linea. È inoltre possibile cercare gli utenti utilizzando il pannello di controllo di Lync Server o lo snap-in utenti e computer di Active Directory.
ms.openlocfilehash: f74c1dfe7f1b8184c59261ff03a01f2f5b39db18
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820246"
---
# <a name="control-panel---updated-user-search"></a>Pannello di controllo (aggiornato): ricerca utenti

È possibile utilizzare i risultati di una query di ricerca per configurare gli utenti di Skype for Business Server. È possibile ricercare utenti in base al nome visualizzato, al nome, al cognome, al nome dell'account SAM (Security Accounts Manager), all'indirizzo SIP o all'URI (Uniform Resource Identifier) della linea. È inoltre possibile cercare gli utenti utilizzando il pannello di controllo di Lync Server o lo snap-in utenti e computer di Active Directory.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina del pannello di controllo della **ricerca utente** è possibile eseguire le attività seguenti:

- [Cercare gli utenti](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Abilitazione o disabilitazione degli utenti](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [Spostare un utente](ms.lync.lscp.UserMove.md)

- [Spostare tutti gli utenti](ms.lync.lscp.UserMoveAll.md)

- [Assegnare i criteri agli utenti](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Abilitare gli utenti per VoIP aziendale in Skype for Business Server](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configurare la Federazione, l'accesso utente remoto e la connettività per la messaggistica istantanea pubblica per gli utenti](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Configurare la telefonia per gli utenti](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)



## <a name="ui-reference"></a>Informazioni sull'interfaccia utente

Nei seguenti elenchi vengono descritti i menu, i comandi, i campi e le proprietà presenti sulla pagina **Ricerca utente**.

### <a name="user-search"></a>Ricerca utente

- **Ricerca** Cercare gli utenti in base alla prima parte del nome visualizzato, del nome, del cognome, del nome dell'account SAM, dell'indirizzo SIP o dell'URI di linea dell'account utente.

- **Ricerca LDAP** Cercare gli utenti digitando un'espressione LDAP.

- **Casella Cerca utenti** Digitare i dati utente o l'espressione LDAP per cui si desidera ricercare.

- **Individuare** Fare clic per visualizzare gli utenti che soddisfano i valori di ricerca immessi negli utenti e nella casella di **ricerca** .

- **Apri query** Fare clic per aprire una query di ricerca salvata.

- **Salva query** Fare clic per salvare una query di ricerca.

- **+ Aggiungi filtro** Fare clic per aggiungere ulteriori criteri di ricerca.

- **Campi filtro di ricerca** Selezionare il campo in cui si desidera filtrare i risultati della ricerca, selezionare un operatore per la query e quindi digitare la stringa di cui si desidera eseguire la ricerca.

- **Numero massimo di utenti da visualizzare** Digitare il numero di risultati di ricerca che si desidera visualizzare oppure utilizzare le frecce su e giù per specificare il numero.

Aggiungere ulteriore testo descrittivo in base alle necessità.

### <a name="search-results-menus"></a>Menu dei risultati della ricerca

- **Abilitare gli utenti** Fare clic per aprire la finestra di dialogo [Users: New Lync Server](ms.lync.lscp.UserNew.md) , in cui è possibile aggiungere un nuovo utente a Skype for Business Server.

    Per aggiungere un nuovo contatto, fare clic sulla freccia verso il basso e selezionare **Abilita contatti** per aprire la finestra di dialogo [Users: New Contact Objects](ms.lync.lscp.UserNewContact.md).

- **Modifica** Fare clic su **modifica** e quindi su **Mostra dettagli** per visualizzare i dettagli dell'utente selezionato oppure fare clic su **Seleziona tutti i risultati della ricerca** per selezionare tutti gli utenti visualizzati nella tabella dei risultati.

- **Azione** Fare clic su **azione**, quindi selezionare l'azione che si desidera eseguire per gli utenti selezionati nei risultati della ricerca. Sono disponibili le azioni seguenti:

  - **Riattivazione per Lync Server** Consente di abilitare l'account utente selezionato dopo che è stato disabilitato temporaneamente.

  - **Disabilitazione temporanea per Lync Server** Disattiva l'account utente in Skype for Business Server fino a quando non lo si riabilita, senza rimuovere l'account utente.

  - **Assegnare i criteri** Apre la finestra di dialogo [utenti: Assegna criteri](ms.lync.lscp.UserAssignPolicy.md) , in cui è possibile configurare i criteri assegnati all'utente.

  - **Visualizzazione dello stato del pin** Apre la finestra di dialogo [utenti: Visualizza stato PIN](ms.lync.lscp.UserViewPin.md) , in cui vengono visualizzati i dati del PIN per l'utente selezionato.

  - **Imposta PIN** Apre la finestra di dialogo [Imposta PIN](ms.lync.lscp.UserSetPin.md) , in cui è possibile impostare il pin per l'utente selezionato.

  - **Pin di blocco** Blocca il PIN per l'utente.

  - **Sblocca PIN** Rimuove il blocco sul PIN dell'utente.

  - **Rimuovi da Lync Server** Rimuove l'account utente da Skype for Business Server. L'utente non viene rimosso da Active Directory.

  - **Rimuovi certificato utente** Rimuove tutti i certificati concessi all'utente.

  - **Spostare gli utenti selezionati nel pool** Apre la finestra di dialogo [Sposta utente](ms.lync.lscp.UserMove.md) , in cui è possibile selezionare il pool in cui spostare l'utente selezionato.

  - **Spostare tutti gli utenti nel pool** Apre la finestra di dialogo [Sposta utente](ms.lync.lscp.UserMove.md) , in cui è possibile selezionare il pool in cui spostare tutti gli utenti selezionati.


