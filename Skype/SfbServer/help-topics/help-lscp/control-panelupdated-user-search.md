---
title: Pannello di controllo-aggiornamento della ricerca degli utenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: È possibile usare i risultati di una query di ricerca per configurare gli utenti per Skype for Business Server. È possibile cercare gli utenti per nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (SAM), indirizzo SIP o URI (Uniform Resource Identifier) linea. È anche possibile cercare gli utenti usando il pannello di controllo di Lync Server o lo snap-in utenti e computer di Active Directory.
ms.openlocfilehash: 75682c6cc732ce94baf312ddae847b5bb8bf37ec
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686829"
---
# <a name="control-panel---updated-user-search"></a>Ricerca utente

È possibile usare i risultati di una query di ricerca per configurare gli utenti per Skype for Business Server. È possibile cercare gli utenti per nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (SAM), indirizzo SIP o URI (Uniform Resource Identifier) linea. È anche possibile cercare gli utenti usando il pannello di controllo di Lync Server o lo snap-in utenti e computer di Active Directory.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

È possibile eseguire le attività seguenti nella pagina del pannello di controllo della **ricerca utente** :

- [Cercare gli utenti di Lync Server 2010](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Abilitare o disabilitare gli utenti per Lync Server 2010](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [Spostare un utente](move-user.md)

- [Spostare tutti gli utenti](move-all-users.md)

- [Assegnare criteri agli utenti](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Abilitare gli utenti per VoIP aziendale in Lync Server 2013](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configurare Federazione, accesso utente remoto e connettività per messaggistica istantanea pubblica per gli utenti](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Configurare la telefonia per gli utenti](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)

Per informazioni dettagliate sulle diverse procedure che è possibile eseguire tramite il pannello di controllo di Skype for Business Server, vedere [gestire Skype for Business server 2015](../../manage/manage.md).

## <a name="ui-reference"></a>Riferimenti UI

Gli elenchi seguenti descrivono i menu, il comando, i campi e le proprietà nella pagina di **ricerca dell'utente** .

### <a name="user-search"></a>Ricerca utente

- **Ricerca** Cercare gli utenti in base alla prima parte del nome visualizzato, nome, cognome, nome dell'account SAM, indirizzo SIP o URI di linea dell'account utente.

- **Ricerca LDAP** Cercare gli utenti digitando un'espressione LDAP.

- **Casella Cerca utenti** Digitare i dati utente o l'espressione LDAP per cui si vuole ricerca.

- **Trovare** Fare clic per visualizzare gli utenti che soddisfano i valori di ricerca immessi nella casella **Cerca utenti** e.

- **Aprire una query** Fare clic per aprire una query di ricerca salvata.

- **Salva query** Fare clic per salvare una query di ricerca.

- **+ Aggiungi filtro** Fare clic per aggiungere altri criteri di ricerca.

- **Campi filtro ricerca** Selezionare il campo in cui si vogliono filtrare i risultati della ricerca, selezionare un operatore per la query e quindi digitare la stringa in cui si vuole eseguire la ricerca.

- **Numero massimo di utenti da visualizzare** Digitare il numero di risultati di ricerca che si desidera visualizzare oppure usare le frecce su e giù per specificare il numero.

Aggiungere ulteriore testo descrittivo, in base alle esigenze.

### <a name="search-results-menus"></a>Menu risultati della ricerca

- **Abilitare gli utenti** Fare clic per aprire la finestra di dialogo [utenti: nuovo utente di Lync Server](users-new-lync-server-user.md) , in cui è possibile aggiungere un nuovo utente a Skype for Business Server.

    Per aggiungere un nuovo contatto, fare clic sulla freccia in giù e quindi selezionare **Abilita contatti** per aprire la finestra di dialogo [nuovi utenti: nuovo oggetto contatto](users-new-contact-objects.md) .

- **Modifica** Fare clic su **modifica** e quindi su **Mostra dettagli** per visualizzare i dettagli dell'utente selezionato oppure fare clic su **Seleziona tutti i risultati della ricerca** per selezionare tutti gli utenti visualizzati nella tabella risultati.

- **Azione** Fare clic su **azione**e quindi selezionare l'azione che si vuole eseguire per gli utenti selezionati nei risultati della ricerca. Sono disponibili le azioni seguenti:

  - **Riattivazione per Lync Server** Abilita l'account utente selezionato dopo che è stato disabilitato temporaneamente.

  - **Disabilitare temporaneamente per Lync Server** Disabilita l'account utente in Skype for Business Server finché non viene riabilitato, senza rimuovere l'account utente.

  - **Assegnare criteri** Apre la finestra di dialogo [utenti: Assegna criteri](users-assign-policies.md) , in cui è possibile configurare i criteri assegnati all'utente.

  - **Visualizzare lo stato del pin** Apre la finestra di dialogo [utenti: Visualizza stato PIN](users-view-pin-status.md) , che Visualizza i dati del PIN per l'utente selezionato.

  - **Imposta PIN** Apre la finestra di dialogo [Imposta PIN](set-pin.md) , in cui è possibile impostare il pin per l'utente selezionato.

  - **Bloccare il pin** Blocca il PIN per l'utente.

  - **Sblocca PIN** Rimuove il blocco sul PIN dell'utente.

  - **Rimuovi da Lync Server** Consente di rimuovere l'account utente da Skype for Business Server. L'utente non viene rimosso da Active Directory.

  - **Rimuovere il certificato utente** Rimuove tutti i certificati concessi all'utente.

  - **Trasferire gli utenti selezionati nel pool** Apre la finestra di dialogo [spostati utente](move-user.md) , in cui è possibile selezionare un pool in cui trasferire l'utente selezionato.

  - **Trasferire tutti gli utenti al pool** Apre la finestra di dialogo [spostati utente](move-user.md) , in cui è possibile selezionare un pool in cui trasferire tutti gli utenti selezionati.


