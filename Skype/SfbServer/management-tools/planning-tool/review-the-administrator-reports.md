---
title: Esaminare i rapporti dell'amministratore in Skype for Business Server 2015
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
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: Nei rapporti di amministrazione sono incluse informazioni dettagliate per la distribuzione e le operazioni. I report vengono generati in base alle selezioni contrassegnate in siti di progettazione. Il progettista può dare valore aggiunto ai rapporti modificando i diagrammi di rete e definendo gli indirizzi IP completi e i nomi di dominio completi (FQDN) dei server, dei pool e dei servizi di bilanciamento del carico.
ms.openlocfilehash: b8c18dcfef28ac93e8c2036fee7f7b105f5c69bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823346"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Esaminare i rapporti dell'amministratore in Skype for Business Server 2015

Nei rapporti di amministrazione sono incluse informazioni dettagliate per la distribuzione e le operazioni. I report vengono generati in base alle selezioni contrassegnate in **siti di progettazione**. Il progettista può dare valore aggiunto ai rapporti modificando i diagrammi di rete e definendo gli indirizzi IP completi e i nomi di dominio completi (FQDN) dei server, dei pool e dei servizi di bilanciamento del carico.

La caratteristica rapporti amministratore consente di:

- [Esaminare il rapporto riepilogativo](review-the-administrator-reports.md#Summary_report)

- [Esaminare il rapporto sui certificati](review-the-administrator-reports.md#Certificates_Report)

- [Esaminare il report del firewall](review-the-administrator-reports.md#Firewall_report)

- [Esaminare il report DNS](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Esaminare il rapporto riepilogativo
<a name="Summary_report"> </a>

Il report amministratore di Skype for business è il primo di quattro rapporti importanti che documentano il progetto in dettaglio. Le informazioni contenute in questo report e gli altri tre rapporti associati sono utili per i team di Information Technology:

![Rapporto di amministrazione riepilogativo generale](../../media/General_Summary_Report_Admin_Report.png)

Nel rapporto riepilogativo vengono elencate informazioni di configurazione generali associate alla rete perimetrale. La posizione, il nome di dominio completo (FQDN) e l'indirizzo IP, il tipo di rete e i commenti specifici di un determinato ruolo sono documentati.

La finestra di progettazione e ogni team che distribuirà, gestirà e gestirà l'infrastruttura dovrebbe esaminare il rapporto riepilogativo per garantire la massima accuratezza e verificare che gli errori siano minimi.

È inoltre possibile visualizzare i report più dettagliati:

- Rapporto certificati

- Rapporto firewall

- Rapporto DNS

## <a name="review-the-certificates-report"></a>Esaminare il rapporto sui certificati
<a name="Certificates_Report"> </a>

Il rapporto certificati contiene tutti i certificati necessari nella distribuzione di Skype for Business Server 2015 consigliata. Lo strumento di pianificazione rappresenta i nomi soggetto e i nomi alternativi del soggetto immessi. Il testo predefinito che viene lasciato inedito potrebbe rappresentare una possibile sfida per il team responsabile della richiesta e dell'emissione dei certificati. Nelle informazioni sui certificati sono inoltre incluse informazioni sull'origine da cui in genere viene emesso il certificato. Se l'infrastruttura non dispone di un'infrastruttura a chiave pubblica (PKI), tutti i certificati possono essere richiesti tramite un provider di certificati pubblico. I campi relativi agli utilizzi chiave avanzati e alla destinazione del rapporto sono molto utili per comprendere lo scopo e il percorso di ogni certificato.

![Rapporto di amministrazione dei certificati](../../media/Certificates_Report_Admin_Report.png)

Esaminare attentamente e assicurarsi di comprendere l'utilizzo e lo scopo di ogni certificato nella distribuzione. Se si verifica un problema relativo a un certificato, determinare il server o il servizio a cui si sta parlando. I certificati in Skype for Business Server 2015 sono utilizzati per due scopi principali:

- Mutual Transport Layer Security (MTLS)-i computer coinvolti nella comunicazione presentano ciascuno un certificato che dimostra la propria identità a un altro computer. Questa operazione è nota come autenticazione del server. La comunicazione non può iniziare finché ogni computer non considera attendibile l'identità dell'altro computer.

- Crittografia-crittografia (Secure Sockets Layer, or SSL, Transport Layer Security o TLS) è uno strumento essenziale per garantire la protezione delle comunicazioni, garantire la privacy e creare un sistema di comunicazione e collaborazione attendibile.

## <a name="review-the-firewall-report"></a>Esaminare il report del firewall
<a name="Firewall_report"> </a>

Skype for Business Server 2015 dispone di una serie potenzialmente complessa di regole del firewall. Lo strumento di pianificazione consente di ridurre questa complessità generando un report che definisce in dettaglio tutti i requisiti del firewall, in base ai criteri di input della finestra di progettazione. L'amministratore del firewall IT sarà in grado di utilizzare tale rapporto per configurare e definire le regole necessarie.

Dal punto di vista della gestione del firewall, il rapporto dovrebbe essere accuratamente esaminato per assicurarsi che non vi siano conflitti con l'uscita dalle regole del firewall e che non esistano criteri o procedure che potrebbero essere violate.

![Rapporto di amministrazione firewall](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Esaminare il report DNS
<a name="DNS_Report"> </a>

Il report DNS, che fa parte del rapporto dell'amministratore, descrive tutte le voci consigliate e note per il DNS (Domain Name System) nelle reti interne, perimetrali ed esterne. Se la finestra di progettazione ha completato le modifiche apportate al diagramma reticolare e tutti gli indirizzi IP e i nomi di dominio completi (FQDN) sono definiti nei rispettivi valori di produzione, il report DNS fornisce una risorsa di configurazione eccellente. Questo rapporto può anche servire come documento di risoluzione dei problemi operativo.

![Report di amministrazione DNS](../../media/DNS_Report_Admin_Report.png)

È consigliabile che il team di gestione DNS riveda accuratamente il report DNS per assicurarsi che non vi siano errori che potrebbero causare difficoltà durante la distribuzione o che potrebbero complicare una sessione di risoluzione dei problemi.

## <a name="see-also"></a>Vedere anche
<a name="DNS_Report"> </a>

[Esame dei rapporti di amministrazione](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
