---
title: Pianificare Sistema telefonico con connettività PSTN in locale in Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Informazioni sulle considerazioni relative alla pianificazione per il sistema telefonico (cloud PBX) con connettività PSTN locale.
ms.openlocfilehash: f8baab67191f32013a9d7a01ddc12f1b04b62c03
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358812"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Pianificare Sistema telefonico con connettività PSTN in locale in Skype for Business Server

> [!Important]
> Skype for business online si ritirerà il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.  Inoltre, la connettività PSTN tra l'ambiente locale e Skype for Business Server o il Cloud Connector Edition e Skype for business online non sarà più supportato.  Informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Informazioni sulle considerazioni relative alla pianificazione per il sistema telefonico (cloud PBX) con connettività PSTN locale.

Questo contenuto è pertinente se si dispone già di Skype for Business Server o di Lync Server 2013 distribuiti in locale. Per altri scenari, vedere [Microsoft telefonia Solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions).

 Sistema telefonico con connettività PSTN locale consente di sfruttare le funzionalità del sistema telefonico (cloud PBX) per gli utenti. Questo può essere utile per gli scenari seguenti:

- Alcuni degli utenti di Skype for business sono ospitati in locale e altri alloggiati in Skype for business online. È ora possibile abilitare le funzionalità e le funzionalità del sistema telefonico per gli utenti ospitati in Skype for business online, ma continuare a utilizzare la connettività PSTN locale.

- Si dispone di una distribuzione locale e si desidera spostare alcuni o tutti gli utenti in Skype for business online, ma continuare a utilizzare la connettività PSTN locale.

    > [!IMPORTANT]
    > Per abilitare correttamente gli utenti per il sistema telefonico con connettività PSTN locale, è necessario che l'indirizzo SIP sia nel proprio dominio. L'utilizzo del dominio predefinito per Microsoft 365 o Office 365, onmicrosoft.com, non è supportato. 

Per ulteriori informazioni sul sistema telefonico, incluse le licenze e i piani, vedere [PSTN Calling plans for Skype for business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Confronto tra funzionalità

Cloud PBX con connettività PSTN locale non offre lo stesso set di funzionalità di una soluzione di VoIP aziendale completamente locale. Per decidere se Cloud PBX con connettività PSTN locale fornirà il set di funzionalità appropriato per la propria organizzazione, vedere [Ecco cosa si ottiene con Cloud PBX](https://go.microsoft.com/fwlink/?LinkId=715517).

## <a name="benefits-and-planning-considerations"></a>Considerazioni relative a vantaggi e pianificazione

> [!CAUTION]
> I dispositivi Lync Phone Edition devono essere aggiornati al firmware minimo necessario nell'ambiente locale prima di passare a Skype for business online.
Se si spostano gli utenti dall'ambiente locale a quello online prima di aggiornare il firmware, gli utenti non saranno in grado di connettersi utilizzando i propri telefoni. Per risolvere il problema, gli utenti devono essere spostati nell'ambiente locale per aggiornare i telefoni al firmware minimo. NON TENTARE DI ESEGUIRE L'AGGIORNAMENTO AL FIRMWARE MINIMO O DI REIMPOSTARE IN MODO RIGIDO IL TELEFONO PRIMA DI RIPORTARE L'UTENTE NELL'AMBIENTE LOCALE.
Se si esegue un ripristino rigido quando il dispositivo non è al minimo firmware, per impostazione predefinita verrà utilizzato l'autenticazione del PIN, che non è supportata in Skype for business online. Per ulteriori informazioni, fare riferimento a [ottenere telefoni per Skype for business online](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Distribuendo sistema telefonico con connettività PSTN locale, è possibile spostare gli utenti nel cloud tramite Skype for business online a proprio piacimento, mantenendo la connettività PSTN locale. Se si dispone di un sistema PBX, è possibile continuare a usarlo per garantire la connettività PSTN per gli utenti che si spostano nel cloud. Dopo che un utente è stato spostato in Skype for business online e nel sistema telefonico, il suo telefono PBX legacy non funzionerà più, ma il numero di telefono verrà indirizzato a uno qualsiasi dei client Skype for business per PC o smartphone e telefoni da tavolo compatibili con Skype for business. Una volta portati, gli utenti di sistema telefonico e gli utenti PBX legacy possono chiamarsi a vicenda normalmente, nonché effettuare/ricevere chiamate PSTN usando il proprio numero di telefono normale.

Potrebbe essere presente una funzionalità personalizzata o un componente aggiuntivo principale del sistema PBX legacy, ad esempio un Call Center. Se la funzionalità personalizzata non è attualmente disponibile nel sistema telefonico, è consigliabile lasciare gli utenti che richiedono la funzionalità personalizzata in locale con il PBX legacy e portare solo gli utenti che non hanno la necessità di accedere alla funzionalità personalizzata al sistema telefonico con connettività PSTN locale.

Per un elenco di sistemi PBX legacy che interagiscono direttamente con Skype for Business Server 2015, vedere l'  [infrastruttura qualificata per Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Se il PBX non è presente nell'elenco, è possibile utilizzare un session border controller per connettere il PBX al sistema telefonico in Skype for business online.

### <a name="network-considerations-for-quality-and-performance"></a>Considerazioni sulla rete per la qualità e le prestazioni

Quando si distribuisce un servizio ospitato sul cloud come sistema telefonico con connettività PSTN locale, è necessario tenere presente quanto segue. In una distribuzione puramente locale di Skype for Business Server 2015 Enterprise Voice, tutta l'infrastruttura e i client si trovano nella rete aziendale. La qualità e le prestazioni della rete, che è fondamentale per l'audio e il video di alta qualità, sono sotto il controllo diretto del personale dell'organizzazione. Con il sistema telefonico con connettività PSTN locale, esistono tre reti coinvolte, due delle quali è responsabile per il cliente, ma solo una delle quali ha il controllo diretto su:

- **Rete di distribuzione multimediale globale di Microsoft** Infrastruttura e rete cloud globale di Microsoft. I server del sistema telefonico e il traffico attraversano questa rete.

- **Interconnect PSTN Enterprise/Cloud** Questa è la rete che connette l'organizzazione al cloud. Questo non è necessariamente lo stesso della connessione Internet generica.

- **La propria rete aziendale** La qualità dei contenuti multimediali in tempo reale dipende fortemente dalla propria rete: in particolare la rete Wi-Fi e la qualità dell'interconnessione utilizzata per raggiungere il cloud.

> [!NOTE]
> Per ulteriori informazioni sull'ottimizzazione delle prestazioni in Skype for business online, vedere [Tune Skype for business online performance](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Prerequisiti per l'utilizzo del sistema telefonico con connettività PSTN locale

Prima di poter configurare il sistema telefonico con connettività PSTN locale e spostare gli utenti in Skype for business online, è necessario confermare che sono disponibili i prerequisiti seguenti:

 **Versioni server locali.** Le versioni dei server nella distribuzione locale devono essere elencate nella tabella seguente per il supporto del sistema telefonico con connettività PSTN locale.


| **Ruolo del server**                                       | **Versioni supportate\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Perimetro federativo\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Route Federation hop successivo server pool interno  <br/> | Skype for Business Server 2015, March 2016 aggiornamento cumulativo 6.0.9319.235 o versione successiva (front-end o Director)  <br/> |
| Server utenti front-end  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edge Server  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Mediation Server  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Le versioni minime supportate sono:

- Skype for Business Server 2015, March 2016 aggiornamento cumulativo 6.0.9319.235

- Lync Server 2013 luglio 2015 aggiornamento cumulativo 5.0.8308.920

\*\*La route di federazione per tutti i domini SIP supportati deve essere instradata attraverso il server Edge di Skype for Business Server 2015 con l'aggiornamento cumulativo di marzo 2016 o superiore. Se il pool di utenti è su Lync Server 2013, il traffico del pool esterno rimarrà su Lync Server 2013 Edge Server. 

Inoltre, è necessario verificare quanto segue:

- **VoIP aziendale locale è configurato e testato per gli utenti locali** Sono inclusi i componenti di connettività PSTN. Per ulteriori informazioni, vedere i seguenti argomenti se si utilizza Skype for Business Server 2015, vedere [Plan for Enterprise Voice in Skype for Business server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) e [deploy VoIP aziendale in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Se si utilizza Lync Server 2013, vedere [Planning for Enterprise Voice in Lync server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) e [Deploying VoIP aziendale in Lync Server 2013](https://technet.microsoft.com/library/gg412876%28v=ocs.15%29.aspx).

- **Sincronizzazione di Active Directory** È necessario configurare la sincronizzazione di Active Directory tramite Azure AD Connect. Per ulteriori informazioni, vedere [Managing Azure ad Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > La versione di AAD Connect utilizzata deve essere Version 1.0.9125.0 o versione successiva. Se si utilizza una versione precedente degli strumenti AAD Connect o DirSync, eseguire l'aggiornamento alla versione supportata. È possibile aggiornare l'installazione corrente e gestire le regole personalizzate definite nell'ambiente in uso. 

- **Configurare la distribuzione ibrida** Se tutti gli utenti di Skype for business sono attualmente ospitati online o in locale oppure, se attualmente si dispone di un mix, è necessario completare la procedura per configurare una distribuzione ibrida di Skype for Business Server o Lync Server 2013, come descritto in [deploy Hybrid connectivity between Skype for Business Server e Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Per ulteriori informazioni di base sulle distribuzioni ibride, vedere [pianificare la connettività ibrida tra Skype for Business Server e Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). 

    Se si utilizza Lync Server 2013, vedere [Lync server 2013 Hybrid](https://technet.microsoft.com/library/jj204805%28v=ocs.15%29.aspx).

- **Consigliato Active Directory Federation Services (AD FS).** È consigliabile distribuire AD FS per supportare l'accesso Single Sign-on. Per ulteriori informazioni, vedere [Active Directory Federation Services (ad FS)](https://technet.microsoft.com/library/cc736690%28v=ws.10%29.aspx).

Per informazioni sulla distribuzione del sistema telefonico, vedere [abilitare gli utenti per il sistema telefonico con connettività PSTN locale in Skype for Business Server](enable-users-for-phone-system.md).


