---
title: Esaminare i report dell'amministratore in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: I report dell'amministratore sono informazioni dettagliate per la distribuzione e le operazioni. I report vengono generati in base alle selezioni contrassegnate nei siti di progettazione. La finestra di progettazione può aggiungere ulteriore valore ai report dell'amministratore modificando i diagrammi di rete e definendo gli indirizzi IP completi e i nomi di dominio completo (FQDN) per server, pool e servizi di bilanciamento del carico.
ms.openlocfilehash: ae6dba3f5967fcd10618a8ab53c754a4f38da748
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816295"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Esaminare i report dell'amministratore in Skype for Business Server 2015

I report dell'amministratore sono informazioni dettagliate per la distribuzione e le operazioni. I report vengono generati in base alle selezioni contrassegnate nei **siti di progettazione**. La finestra di progettazione può aggiungere ulteriore valore ai report dell'amministratore modificando i diagrammi di rete e definendo gli indirizzi IP completi e i nomi di dominio completo (FQDN) per server, pool e servizi di bilanciamento del carico.

La caratteristica rapporti amministratore consente di:

- [Rivedere il report di riepilogo](review-the-administrator-reports.md#Summary_report)

- [Rivedere il report certificati](review-the-administrator-reports.md#Certificates_Report)

- [Esaminare il report del firewall](review-the-administrator-reports.md#Firewall_report)

- [Rivedere il report DNS](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Rivedere il report di riepilogo
<a name="Summary_report"> </a>

Il report amministratore di Skype for business è il primo di quattro report importanti che documentano la progettazione in dettaglio. Le informazioni contenute in questo report e gli altri tre report associati sono utili per i team di Information Technology:

![Rapporto di amministrazione riepilogativo generale](../../media/General_Summary_Report_Admin_Report.png)

Il report riepilogativo elenca le informazioni generali sulla configurazione associate alla rete Edge. La posizione, il nome di dominio completo (FQDN) e l'indirizzo IP, il tipo di rete e i commenti specifici di un determinato ruolo sono documentati.

La finestra di progettazione e ogni team che distribuirà, gestirà e manterrà l'infrastruttura dovrebbe rivedere il rapporto di riepilogo per l'accuratezza e verificare che gli errori siano minimi.

È anche possibile visualizzare report più dettagliati:

- Report certificati

- Report firewall

- Report DNS

## <a name="review-the-certificates-report"></a>Rivedere il report certificati
<a name="Certificates_Report"> </a>

Il report certificati contiene tutti i certificati necessari nella distribuzione di Skype for Business Server 2015 consigliata. Lo strumento di pianificazione rappresenta i nomi di oggetto e i nomi alternativi oggetto immessi. Il testo predefinito lasciato inedito può rappresentare una potenziale sfida per il team responsabile per richiedere e rilasciare i certificati. Le informazioni sui certificati contengono anche informazioni sulla posizione in cui il certificato può in genere essere emesso. Se l'infrastruttura non ha un'infrastruttura a chiave pubblica (PKI) interna, tutti i certificati possono essere richiesti tramite un provider di certificati pubblici. Gli utilizzi delle chiavi estese (EKU) e i campi assegna ai nel report sono molto utili per capire qual è lo scopo e la posizione per ogni certificato.

![Rapporto di amministrazione certificati](../../media/Certificates_Report_Admin_Report.png)

Esaminare con attenzione e assicurarsi di comprendere l'uso e lo scopo di ogni certificato nella distribuzione. In caso di domande su cosa fa un certificato, determinare il server o il servizio a cui si sta parlando. I certificati in Skype for Business Server 2015 vengono usati per due scopi principali:

- MTLS (Mutual Transport Layer Security)-i computer coinvolti nella comunicazione presentano ognuno un certificato che ne dimostra l'identità a un altro computer. Questa operazione è nota come autenticazione server. La comunicazione non può iniziare finché ogni computer non considera attendibile l'identità dell'altro computer.

- La crittografia-crittografia (Secure Sockets Layer o SSL e Transport Layer Security o TLS) è un mezzo essenziale per garantire la sicurezza delle comunicazioni, per garantire la privacy e per creare un sistema di comunicazione e collaborazione attendibile.

## <a name="review-the-firewall-report"></a>Esaminare il report del firewall
<a name="Firewall_report"> </a>

Skype for Business Server 2015 ha un set di regole firewall potenzialmente complesso. Lo strumento di pianificazione riduce questa complessità generando un report che definisce in dettaglio tutti i requisiti del firewall, in base ai criteri di input della finestra di progettazione. L'amministratore del firewall IT sarà in grado di usare questo report per configurare e definire le regole necessarie.

Dal punto di vista della gestione del firewall, il report deve essere attentamente esaminato per verificare che non ci siano conflitti con l'uscita dalle regole del firewall e che non ci siano criteri o procedure che potrebbero essere violate.

![Rapporto di amministrazione firewall](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Rivedere il report DNS
<a name="DNS_Report"> </a>

Il report DNS, che fa parte del report Administrator, descrive in dettaglio tutte le voci consigliate e note per il DNS (Domain Name System) nelle reti interne, perimetrali ed esterne. Se la finestra di progettazione ha completato le modifiche al diagramma reticolare e tutti gli indirizzi IP e i nomi di dominio completi (FQDN) sono definiti nei rispettivi valori di produzione, il report DNS fornisce una risorsa di configurazione eccellente. Questo report può fungere anche da documento di risoluzione dei problemi operativi.

![Rapporto di amministrazione DNS](../../media/DNS_Report_Admin_Report.png)

Il team di gestione DNS dovrebbe rivedere accuratamente il report DNS per verificare che non ci siano errori che potrebbero causare difficoltà durante la distribuzione o che potrebbero complicare una sessione di risoluzione dei problemi.

## <a name="see-also"></a>Vedere anche
<a name="DNS_Report"> </a>

[Esame dei rapporti amministratore](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
