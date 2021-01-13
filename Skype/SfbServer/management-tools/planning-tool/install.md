---
title: Installare lo strumento di pianificazione in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Prima di iniziare a progettare e pianificare l'infrastruttura di Skype for Business Server 2015 utilizzando lo strumento di pianificazione di Skype for Business Server 2015, è necessario innanzitutto installare lo strumento di pianificazione. Non è necessario distribuire lo strumento di pianificazione su una workstation o un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Skype for Business Server 2015. Il file Readme che accompagna lo strumento di pianificazione descrive in dettaglio informazioni importanti sull'installazione e l'utilizzo dello strumento. Alcune delle informazioni contenute nel file Leggimi vengono riportate in questo argomento per maggiore chiarezza.
ms.openlocfilehash: 902249e042694a37594c6dc0b753b0c1388c0729
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834726"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Installare lo strumento di pianificazione in Skype for Business Server 2015

Prima di iniziare a progettare e pianificare l'infrastruttura di Skype for Business Server 2015 utilizzando lo strumento di pianificazione di Skype for Business Server 2015, è necessario innanzitutto installare lo strumento di pianificazione. Non è necessario distribuire lo strumento di pianificazione su una workstation o un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Skype for Business Server 2015. Il file Readme che accompagna lo strumento di pianificazione descrive in dettaglio informazioni importanti sull'installazione e l'utilizzo dello strumento. Alcune delle informazioni contenute nel file Leggimi vengono riportate in questo argomento per maggiore chiarezza.

> [!IMPORTANT]
> Lo strumento di pianificazione richiede l'installazione da parte di un utente con autorizzazioni e diritti di amministratore nel computer in cui deve essere installato lo strumento.

I sistemi operativi supportati per l'installazione e l'esecuzione dello strumento di pianificazione sono i seguenti:

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, edizione a 32 bit

- Windows 7, edizione a 64 bit con Windows on Win32 (WOW)

- Windows Server 2008 R2, con WOW

Inoltre, lo strumento di pianificazione richiede Microsoft .NET Framework 4,5.

Dopo aver soddisfatto i requisiti di preinstallazione, è possibile installare lo strumento di pianificazione.



## <a name="to-install-the-planning-tool"></a>Per installare lo strumento di pianificazione

1. Accedere al computer locale come membro del gruppo Administrators.

2. Se si utilizza Esplora risorse o una finestra di comando, individuare la directory in cui sono stati scaricati i file di installazione dello strumento di pianificazione.

3. Individuare il SkypeForBusinessPlanningTool.msi. In Esplora risorse fare doppio clic sul file. Nella finestra di comando, digitare il nome del file e quindi premere **invio** per eseguire il file.

4. Nella pagina iniziale dell' **installazione guidata dello strumento di pianificazione di Skype for Business Server 2015** fare clic su **Avanti**.

5. Leggere il **Contratto di Licenza con l'utente finale**, selezionare **Accetto i termini del Contratto di Licenza** se si sceglie di accettare le condizioni per l'utilizzo riportate nel contratto e quindi fare clic su **Avanti**.

6. Scegliere dove installare i file dello strumento di pianificazione. Il percorso predefinito è C:\Program Files (x86) \Skype for Business Server 2015 \ Planning Tool. Se si desidera cambiarlo, fare clic su **Cambia**. In **Modifica cartella di destinazione**, individuare o digitare il percorso in cui installare i file, fare clic su **OK** e quindi su **Avanti**.

7. Il programma di installazione è ora pronto per installare lo strumento di pianificazione. Fare clic su **Installa** per avviare il processo di installazione.

8. L'installazione verrà avviata e verrà visualizzato il relativo stato. Al termine dell'installazione, fare clic su **Fine**.

9. Lo strumento di pianificazione è pronto per l'uso.

## <a name="optional-software"></a>Software facoltativo
<a name="Optional_Software"> </a>

Lo strumento di pianificazione di Skype for Business Server 2015 è stato progettato per essere esportato in Microsoft Excel e Microsoft Visio. Anche se queste applicazioni non sono necessarie per il funzionamento dello strumento di pianificazione, aggiungono un valore significativo alla distribuzione e alla documentazione del progetto.

### <a name="microsoft-excel"></a>Microsoft Excel

L'esportazione del progetto in Microsoft Excel consente di creare un report in cui vengono visualizzate sette schede nel foglio di calcolo:

- Riepilogo: consente di visualizzare informazioni sulla configurazione del sito, inclusi il numero di utenti, le impostazioni di capacità e le informazioni sui profili del server.

- Profilo hardware: consente di visualizzare un report sulle configurazioni hardware consigliate per i server specificati nella topologia, tra cui CPU, memoria, disco e interfaccia di rete. Sono incluse anche la quantità e le specifiche consigliate per i componenti del server. Ogni server è inoltre definito dal sito per fornire una rappresentazione completa dei requisiti del server in base al sito.

- Requisiti per le porte: consente di visualizzare un report di tutte le porte abilitate e l'associazione al bilanciamento del carico del sistema DNS (Domain Name System) e ai sistemi di bilanciamento del carico hardware (HLB). È consigliabile utilizzare questo report per pianificare le configurazioni di firewall e di LB e di HLB di DNS.

- Report riepilogativo-Visualizza il riepilogo generale delle impostazioni necessarie per configurare la rete del server perimetrale.

- Report certificati: Visualizza il nome del soggetto e i nomi alternativi del soggetto necessari per i certificati necessari per ottenere i server perimetrali in esecuzione.

- Report firewall-consente di visualizzare le porte di origine e di destinazione e gli indirizzi IP per le interfacce sia esterne che interne.

- Report DNS: consente di visualizzare gli indirizzi di dominio completo (FQDN) e IP/VIP necessari per ogni voce DNS creata.

### <a name="microsoft-visio"></a>Microsoft Visio

L'esportazione del progetto in Microsoft Visio consente di creare un diagramma da usare per la documentazione della topologia e dell'infrastruttura configurate. Il diagramma importato può essere modificato e riorganizzato in base alle specifiche esigenze per la documentazione. Il diagramma di Visio tipico includerà:

> [!NOTE]
> Se il progetto è sufficientemente grande da richiedere più di tre Front End Server, verrà creata una pagina aggiuntiva per il pool Front End, i Front End Server, il computer che esegue SQL Server, gli indirizzi IP e i nomi FQDN.

- Topologia globale-diagramma dei siti di Skype for Business Server 2015 configurati.

- Scheda nome sito-consente di visualizzare la topologia di configurazione del sito con server perimetrale, firewall, rete PSTN (Public Switched Telephone Network) con gateway e la distribuzione del server interno. La distribuzione interna è costituita da server e pool configurati, inclusi i pool Front End, i server basati su SQL Server, i servizi di dominio Active Directory, i direttori, i server di messaggistica unificata di Exchange, i server cassette postali di Exchange, i server Office Web Apps, i Mediation Server e i server Chat persistente.

- Diagramma di rete perimetrale-diagramma in cui viene illustrata la configurazione del server perimetrale con gli indirizzi IP e gli FQDN associati. Sono inoltre inclusi il bilanciamento del carico DNS e i dispositivi di bilanciamento del carico hardware. Vengono inoltre visualizzati i direttori e il front end server o il pool Front End, con DNS LB o HLB associato e l'indirizzo IP assegnato (lo strumento di pianificazione supporta sia gli indirizzi IPv4 che IPv6) e il nome di dominio completo.

## <a name="see-also"></a>Vedere anche
<a name="Optional_Software"> </a>

[Installazione dello strumento di pianificazione](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
