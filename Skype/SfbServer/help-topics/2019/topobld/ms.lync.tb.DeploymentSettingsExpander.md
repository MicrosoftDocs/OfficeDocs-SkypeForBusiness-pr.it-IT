---
title: Espansione delle impostazioni di distribuzione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DeploymentSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7220ec1f-38cb-4297-870e-591a832cd2f2
ROBOTS: NOINDEX, NOFOLLOW
description: 'È possibile modificare le proprietà di una distribuzione esistente con le sezioni seguenti:'
ms.openlocfilehash: 84e4873b098c6d3cf650c71653456b22179fa44c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189008"
---
# <a name="deployment-settings-expander"></a>Espansione delle impostazioni di distribuzione

È possibile modificare le proprietà di una distribuzione esistente con le sezioni seguenti:

- Dominio SIP

- URL semplici

- Server di gestione centrale

## <a name="sip-domain"></a>Dominio SIP

Per modificare il valore del campo **Dominio SIP predefinito**, immettere il nuovo nome di dominio.

Per aggiungere **Domini SIP aggiuntivi supportati**, digitare il nome del dominio desiderato e fare clic su **Aggiungi** per accettarlo come nuovo nome di dominio SIP (Session Initiation Protocol).

Per aggiornare un nome di dominio SIP aggiuntivo esistente, selezionare il nome e apportare le modifiche nella casella di testo. Fare clic su **Aggiorna** per accettare la modifica.

Per rimuovere un nome di dominio SIP aggiuntivo definito, selezionare il nome e fare clic su **Rimuovi**.

Dopo aver apportato tutte le modifiche desiderate nella pagina Modifica proprietà, fare clic su **OK** per salvarle. Fare clic su **Annulla** per rimuoverle.

## <a name="simple-urls"></a>URL semplici

Per modificare o definire gli URL semplici, è necessario decidere quale dei tre URL semplici si vuole modificare o cambiare. È possibile scegliere tra l'URL di accesso a telefono, l'URL riunione e l'URL di accesso amministrativo.

Per modificare l'URL di accesso a telefono o l'URL riunione, selezionare l'URL da cambiare e fare clic su **Modifica URL**. Modificare quindi l'URL e fare clic su **OK** per salvarlo. Fare clic su **Annulla** per rimuovere le modifiche.

Per aggiungere un nuovo URL, fare clic su **Aggiungi**. Nella finestra di dialogo **Aggiungi URL semplice** specificare l'URL e fare clic su **OK** per salvarlo. Selezionare **Rendi attivo l'URL corrente per il dominio selezionato** se è necessario impostare il nuovo URL come URL attivo. Fare clic su **Annulla** per rimuovere le modifiche.

Per impostare un altro URL come URL attivo (contrassegnato da un segno di spunta verde), selezionare l'URL desiderato e fare clic su **Rendi attivo**.

> [!NOTE]
> È consentito un solo URL attivo per ogni dominio SIP.

Se è necessario rimuovere un URL, selezionarlo e fare clic su **Rimuovi**.

> [!CAUTION]
> Leggere attentamente le informazioni nella finestra di dialogo relativa alle impostazioni degli URL semplici. La rimozione di un URL riunione potrebbe rendere inaccessibili le riunioni pianificate dagli utenti. Considerare l'eventualità di lasciare l'URL precedente dopo aver impostato come attivo il nuovo URL riunione. Quando si è certi che gli utenti non utilizzano più l'URL riunione precedente, è possibile rimuoverlo senza problemi.

Per modificare o cambiare l'URL di accesso amministrativo, modificare la voce corrispondente.

Dopo aver apportato tutte le modifiche desiderate nella pagina Modifica proprietà, fare clic su **OK** per salvarle. Fare clic su **Annulla** per rimuoverle.

## <a name="central-management-server"></a>Server di gestione centrale

È possibile spostare il server di gestione centrale da un pool Front End definito a un altro pool Front End definito. Per cambiare la posizione del server di gestione centrale, selezionare il pool Front End nell'elenco a discesa in **Server Front End in cui installare il server di gestione centrale**. Un Front End Server può essere un pool Enterprise Edition Front End o uno Standard Edition Front End Server.

> [!IMPORTANT]
> Dopo aver definito, pubblicato e distribuito l'archivio di gestione centrale per l'infrastruttura, non sarà possibile cambiare la posizione di tale archivio senza spostarlo in un altro Front End tramite un processo esterno.

Per informazioni dettagliate sullo spostamento dell'archivio di gestione centrale, vedere [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps) nelle informazioni di riferimento sui cmdlet di Windows PowerShell.


Per informazioni dettagliate sulla definizione e sulla configurazione di queste impostazioni, vedere [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx).


