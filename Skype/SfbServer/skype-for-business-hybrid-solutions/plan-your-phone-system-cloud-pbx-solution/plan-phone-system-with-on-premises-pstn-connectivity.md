---
title: Pianificare Sistema telefonico con connettività PSTN locale in Skype for Business Server
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
description: Informazioni sulle considerazioni sulla pianificazione per Sistema telefonico (Cloud PBX) con connettività PSTN locale.
ms.openlocfilehash: f8baab67191f32013a9d7a01ddc12f1b04b62c03
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358812"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Pianificare Sistema telefonico con connettività PSTN locale in Skype for Business Server

> [!Important]
> Skype for Business online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.  Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business online non sarà più supportata.  Informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Informazioni sulle considerazioni sulla pianificazione per Sistema telefonico (Cloud PBX) con connettività PSTN locale.

Questo contenuto è pertinente se Skype for Business Server o Lync Server 2013 è già distribuito in locale. Per altri scenari, vedere Soluzioni [di telefonia Microsoft.](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)

 Sistema telefonico con connettività PSTN locale consente di sfruttare le funzionalità di Sistema telefonico (Cloud PBX) per gli utenti. Ciò può essere utile per gli scenari seguenti:

- Alcuni utenti di Skype for Business sono ospitati in locale e altri in Skype for Business online. È ora possibile abilitare le funzionalità e le funzionalità del sistema telefonico per gli utenti ospitati in Skype for Business online, ma continuare a usare la connettività PSTN locale.

- Si dispone di una distribuzione locale e si desidera spostare alcuni o tutti gli utenti in Skype for Business online, ma continuare a usare la connettività PSTN locale.

    > [!IMPORTANT]
    > Per abilitare correttamente gli utenti per Sistema telefonico con connettività PSTN locale, il relativo indirizzo SIP deve essere nel proprio dominio. L'uso del dominio predefinito per Microsoft 365 o Office 365, onmicrosoft.com, non è supportato. 

Per altre informazioni su Sistema telefonico, incluse licenze e piani, vedi Piani per chiamate [PSTN per Skype for Business.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)

## <a name="feature-comparison"></a>Confronto delle funzionalità

Cloud PBX con connettività PSTN locale non offre lo stesso set di funzionalità di una soluzione VoIP aziendale locale. Per decidere se Cloud PBX con connettività PSTN locale fornirà il set di funzionalità giusto per l'organizzazione, vedere Ecco cosa si ottiene [con Cloud PBX.](https://go.microsoft.com/fwlink/?LinkId=715517)

## <a name="benefits-and-planning-considerations"></a>Considerazioni sui vantaggi e sulla pianificazione

> [!CAUTION]
> I dispositivi Lync Phone Edition DEVONO essere aggiornati al firmware minimo necessario nell'ambiente locale prima di passare a Skype for Business online.
Se si spostano gli utenti dall'ambiente locale a quello online prima di aggiornare il firmware, gli utenti non saranno in grado di connettersi utilizzando i loro telefoni. Per risolvere il problema, gli utenti devono essere spostati di nuovo nell'ambiente locale per aggiornare i loro telefoni al firmware minimo. NON TENTARE DI ESEGUIRE L'AGGIORNAMENTO AL FIRMWARE MINIMO O DI REIMPOSTARE IL TELEFONO PRIMA DI SPOSTARE DI NUOVO L'UTENTE NELL'AMBIENTE LOCALE.
Se viene eseguito un hard reset mentre il dispositivo non è almeno firmware, per impostazione predefinita verrà utilizzato l'autenticazione PIN, che non è supportata in Skype for Business online. Per altre informazioni, fare riferimento a [Ottenere telefoni per Skype for Business online.](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)

Distribuendo Sistema telefonico con connettività PSTN locale, è possibile spostare gli utenti nel cloud tramite Skype for Business online al proprio ritmo, mantenendo la connettività PSTN locale. Se si dispone di un sistema PBX, continuare a utilizzarlo per fornire connettività PSTN agli utenti che si spostano nel cloud. Una volta spostato un utente in Skype for Business online e Sistema telefonico, il telefono PBX legacy non funzionerà più, ma il numero di telefono verrà instradato a uno qualsiasi dei client Skype for Business per PC o smartphone, nonché ai telefoni da tavolo compatibili con Skype for Business. Dopo la portabilità, gli utenti di Sistema telefonico e gli utenti PBX legacy possono chiamarsi normalmente, nonché effettuare/ricevere chiamate PSTN utilizzando il loro normale numero di telefono.

Potrebbe essere disponibile una funzionalità personalizzata o un componente aggiuntivo principale per il PBX legacy, ad esempio un call center. Se la funzionalità personalizzata non è attualmente disponibile in Sistema telefonico, lasciare gli utenti che richiedono tale funzionalità personalizzata in locale con il PBX legacy e convertire gli utenti che non devono accedere alla funzionalità personalizzata in Sistema telefonico con connettività PSTN locale.

Per un elenco dei sistemi PBX legacy che interagisce direttamente con Skype for Business Server 2015, vedere [Infrastruttura qualificata per Microsoft Lync.](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway) Se il pbx non è in questo elenco, è possibile utilizzare un Session Border Controller per connettere il PBX al sistema telefonico in Skype for Business online.

### <a name="network-considerations-for-quality-and-performance"></a>Considerazioni sulla rete per la qualità e le prestazioni

Quando si distribuisce un servizio ospitato nel cloud come Sistema telefonico con connettività PSTN locale, è necessario tenere presente quanto segue. In una distribuzione di Skype for Business Server 2015 VoIP aziendale locale, tutta l'infrastruttura e i client sono nella propria rete aziendale. La qualità e le prestazioni di questa rete, fondamentale per audio e video di alta qualità, sono sotto il controllo diretto del personale aziendale. Con Sistema telefonico con connettività PSTN locale, sono coinvolte tre reti, due delle quali sono responsabili del cliente, ma solo una delle quali il personale aziendale ha il controllo diretto su:

- **Rete di distribuzione multimediale globale di Microsoft** Infrastruttura e rete cloud globale di Microsoft. I server del sistema telefonico e il traffico attraversano la rete.

- **Interconnetto PSTN aziendale/cloud** Questa è la rete che connette l'azienda al cloud. Questo non è necessariamente lo stesso della connessione Internet generica.

- **Rete aziendale** La qualità dei supporti in tempo reale dipende in larga parte dalla tua rete, in particolare dalla rete WiFi e dalla qualità dell'interconnessione usata per raggiungere il cloud.

> [!NOTE]
> Per ulteriori informazioni sull'ottimizzazione delle prestazioni in Skype for Business online, vedere [Ottimizzare le prestazioni di Skype for Business online.](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US) 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Prerequisiti per l'utilizzo di Sistema telefonico con connettività PSTN locale

Prima di poter configurare Sistema telefonico con connettività PSTN locale e spostare gli utenti in Skype for Business online, è necessario verificare di disporre dei prerequisiti seguenti:

 **Versioni server locali.** Le versioni dei server nella distribuzione locale devono essere elencate nella tabella seguente per supportare Sistema telefonico con connettività PSTN locale.


| **Ruolo del server**                                       | **Versioni supportate\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Server perimetrale federativo\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Server pool interno route federazione hop successivo  <br/> | Aggiornamento cumulativo per Skype for Business Server 2015, marzo 2016 6.0.9319.235 o versione successiva (Front End o Director)  <br/> |
| Front End User Server  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edge Server  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Mediation Server  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Le versioni minime supportate sono:

- Aggiornamento cumulativo 6.0.9319.235 di Skype for Business Server 2015, marzo 2016

- Lync Server 2013 Aggiornamento cumulativo 5.0.8308.920 di luglio 2015

\*\*La route di federazione per tutti i domini SIP supportati deve essere instradato attraverso il server perimetrale Skype for Business Server 2015 che esegue l'aggiornamento cumulativo di marzo 2016 o versione successiva. Se il pool di utenti si trova in Lync Server 2013, il traffico del pool esterno rimane nel server perimetrale Lync Server 2013. 

È inoltre necessario verificare quanto segue:

- **I VoIP aziendale locali sono configurati e testati per gli utenti locali** Sono inclusi i componenti di connettività PSTN. Per ulteriori informazioni, vedere i seguenti argomenti se si utilizza Skype for Business Server 2015, vedere [Pianificare VoIP aziendale in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) e Distribuire VoIP aziendale in Skype for Business Server [2015.](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)

    Se si utilizza Lync Server 2013, vedere Pianificazione di [VoIP aziendale in Lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) e Distribuzione di VoIP aziendale in Lync Server [2013.](https://technet.microsoft.com/library/gg412876%28v=ocs.15%29.aspx)

- **Sincronizzazione di Active Directory** È necessario configurare la sincronizzazione di Active Directory con Azure AD Connect. Per ulteriori informazioni, vedere [Gestione di Azure AD Connect.](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)

    > [!NOTE]
    > La versione di AAD Connect in uso deve essere la versione 1.0.9125.0 o successiva. Se si utilizza una versione precedente degli strumenti di AAD Connect o DirSync, eseguire l'aggiornamento alla versione supportata. È possibile aggiornare l'installazione corrente e gestire tutte le regole personalizzate definite nell'ambiente. 

- **Configurare la distribuzione ibrida** Sia che tutti gli utenti di Skype for Business siano attualmente ospitati online o locali o se si dispone di una combinazione, è necessario completare la procedura per configurare una distribuzione ibrida di Skype for Business Server o Lync Server 2013, come descritto in Distribuire la connettività ibrida tra Skype for Business Server e [Office 365.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md) Per ulteriori informazioni di base sulle distribuzioni ibride, vedere Pianificare la connettività ibrida [tra Skype for Business Server e Office 365.](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 

    Se si utilizza Lync Server 2013, vedere [Lync Server 2013 ibrido.](https://technet.microsoft.com/library/jj204805%28v=ocs.15%29.aspx)

- **(Consigliato) Active Directory Federation Services (AD FS).** È consigliabile distribuire AD FS per supportare Single Sign-On. Per ulteriori informazioni, vedere [Active Directory Federation Services (AD FS)](https://technet.microsoft.com/library/cc736690%28v=ws.10%29.aspx).

Per informazioni sulla distribuzione di Sistema telefonico, vedere Abilitare gli utenti per Sistema telefonico con connettività [PSTN locale in Skype for Business Server.](enable-users-for-phone-system.md)


