---
title: Installare lo strumento di pianificazione in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Prima di iniziare a progettare e pianificare l'infrastruttura Skype for Business Server 2015 utilizzando lo strumento di pianificazione di Skype for Business Server 2015, è necessario installare lo strumento di pianificazione. Lo strumento di pianificazione non deve essere distribuito in una workstation o in un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Skype for Business Server 2015. Il file Readme che accompagna lo strumento di pianificazione contiene informazioni importanti sull'installazione e sull'utilizzo dello strumento. Alcune delle informazioni contenute nel file Leggimi vengono riportate in questo argomento per maggiore chiarezza.
ms.openlocfilehash: 5d9dc6204647daf03adfab6fcf3cf091d7ba5415
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850889"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Installare lo strumento di pianificazione in Skype for Business Server 2015

Prima di iniziare a progettare e pianificare l'infrastruttura Skype for Business Server 2015 utilizzando lo strumento di pianificazione di Skype for Business Server 2015, è necessario installare lo strumento di pianificazione. Lo strumento di pianificazione non deve essere distribuito in una workstation o in un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Skype for Business Server 2015. Il file Readme che accompagna lo strumento di pianificazione contiene informazioni importanti sull'installazione e sull'utilizzo dello strumento. Alcune delle informazioni contenute nel file Leggimi vengono riportate in questo argomento per maggiore chiarezza.

> [!IMPORTANT]
> Lo strumento di pianificazione richiede l'installazione da parte di un utente con diritti e autorizzazioni di amministratore nel computer in cui deve essere installato lo strumento.

I sistemi operativi supportati per l'installazione e il funzionamento dello strumento di pianificazione sono:

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, edizione a 32 bit

- Windows 7, edizione a 64 bit con Windows on Win32 (WOW)

- Windows Server 2008 R2, con WOW

Inoltre, lo strumento di pianificazione richiede Microsoft .NET Framework 4.5.

Dopo aver soddisfatto i requisiti di preinstallazione, è possibile installare lo strumento di pianificazione.



## <a name="to-install-the-planning-tool"></a>Per installare lo strumento di pianificazione

1. Accedere al computer locale come membro del gruppo Administrators.

2. Utilizzando Windows Explorer o una finestra di comando, individuare la directory in cui sono stati scaricati i file di installazione dello strumento di pianificazione.

3. Individuare il SkypeForBusinessPlanningTool.msi. In Windows Explorer fare doppio clic sul file. Nella finestra di comando digitare il nome del file e quindi premere **INVIO** per eseguire il file.

4. Nella pagina iniziale dell'installazione guidata **Skype for Business Server 2015, Planning Tool Setup Wizard,** fare clic su **Avanti.**

5. Leggere il **Contratto di Licenza con l'utente finale**, selezionare **Accetto i termini del Contratto di Licenza** se si sceglie di accettare le condizioni per l'utilizzo riportate nel contratto e quindi fare clic su **Avanti**.

6. Scegliere dove installare i file dello strumento di pianificazione. Il percorso predefinito è C:\Programmi (x86)\Skype for Business Server 2015\Strumento di pianificazione. Se si desidera cambiarlo, fare clic su **Cambia**. In **Modifica cartella di destinazione**, individuare o digitare il percorso in cui installare i file, fare clic su **OK** e quindi su **Avanti**.

7. Il programma di installazione è ora pronto per installare lo strumento di pianificazione. Fare clic su **Installa** per avviare il processo di installazione.

8. L'installazione verrà avviata e verrà visualizzato il relativo stato. Al termine dell'installazione, fare clic su **Fine**.

9. Lo strumento di pianificazione è pronto per l'uso.

## <a name="optional-software"></a>Software facoltativo
<a name="Optional_Software"> </a>

Lo Skype for Business Server 2015 Planning Tool è progettato per l'esportazione in Microsoft Excel e Microsoft Visio. Anche se queste applicazioni non sono necessarie per il funzionamento dello strumento di pianificazione, aggiungono un valore significativo alla distribuzione e alla documentazione della progettazione.

### <a name="microsoft-excel"></a>Microsoft Excel

Esportando la struttura in Microsoft Excel viene creato un report che visualizza sette schede nel foglio di calcolo:

- Riepilogo: visualizza informazioni sulla configurazione del sito, tra cui il numero di utenti, le impostazioni di capacità e le informazioni sul profilo del server.

- Profilo hardware - Visualizza un report sulle configurazioni hardware consigliate per i server specificati nella topologia, tra cui CPU, memoria, disco e interfaccia di rete. Sono incluse anche la quantità e le specifiche consigliate per i componenti server. Inoltre, ogni server viene definito dal sito per fornire una rappresentazione completa dei requisiti del server in base al sito.

- Requisiti delle porte- Visualizza un report di tutte le porte abilitate e l'associazione al bilanciamento del carico DNS (Domain Name System) e ai servizi di bilanciamento del carico hardware (HLB). È consigliabile utilizzare questo report per pianificare le configurazioni firewall e DNS LB e HLB.

- Rapporto riepilogativo- Visualizza il riepilogo generale delle impostazioni necessarie per configurare la rete di server perimetrali.

- Rapporto certificati - Visualizza il nome soggetto e i nomi alternativi soggetto necessari per i certificati necessari per l'esecuzione dei server perimetrali.

- Rapporto firewall - Visualizza le porte di origine e di destinazione e gli indirizzi IP per le interfacce esterne e interne.

- Rapporto DNS - Visualizza il nome di dominio completo (FQDN) e gli indirizzi IP/VIP necessari per ogni voce DNS creata.

### <a name="microsoft-visio"></a>Microsoft Visio

L'esportazione del progetto in Microsoft Visio consente di creare un diagramma da usare per la documentazione della topologia e dell'infrastruttura configurate. Il diagramma importato può essere modificato e riorganizzato in base alle specifiche esigenze per la documentazione. Il diagramma di Visio tipico includerà:

> [!NOTE]
> Se la struttura è sufficientemente grande da richiedere più di tre Front End Server, verrà creata una pagina aggiuntiva per il pool Front End, i Front End Server, il computer che esegue SQL Server, gli indirizzi IP e gli FQDN.

- Topologia globale - Diagramma dei siti Skype for Business Server 2015.

- Scheda Nome sito - Visualizza la topologia di configurazione del sito con server perimetrali, firewall, PSTN (Public Switched Telephone Network) con gateway e la distribuzione interna del server. La distribuzione interna è costituita da server e pool configurati, inclusi pool Front End, server basati su SQL Server, Servizi di dominio Active Directory, Director, server messaggistica unificata Exchange, server Cassette postali Exchange, server Web Apps Office, Mediation Server e server Chat persistente.

- Edge Network Diagram - Diagramma che illustra in dettaglio la configurazione del server perimetrale con indirizzi IP e FQDN associati. Sono inoltre inclusi il bilanciamento del carico DNS e i dispositivi di bilanciamento del carico hardware. Vengono inoltre visualizzati i Director e il Front End Server o il pool Front End, con LB DNS o HLB associati e l'indirizzo IP assegnato (lo strumento di pianificazione supporta sia gli indirizzi IPv4 che IPv6) e FQDN.

## <a name="see-also"></a>Vedere anche
<a name="Optional_Software"> </a>

[Installazione dello strumento di pianificazione](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)