---
title: Pianificare l'esperienza client di Skype for business 2015 per gli utenti
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: "Riepilogo: informazioni sul nuovo Skype for business e sui passaggi che è possibile eseguire per preparare l'ambiente e gli utenti per l'aggiornamento, se si sta utilizzando Skype for business online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013 o Lync Server 2010."
ms.openlocfilehash: c1fecbdb5a4ec0a19e464a57ee128d2d00ad501f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777751"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Pianificare l'esperienza client di Skype for business 2015 per gli utenti
 
**Riepilogo:** Informazioni sul nuovo Skype for business e sui passaggi che è possibile eseguire per preparare l'ambiente e gli utenti per l'aggiornamento, indipendentemente dal fatto che si utilizzi Skype for business online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013 o Lync Server 2010.
  
Il 14 aprile 2015 Office Update per Lync 2013 include la nuova interfaccia utente di Skype for business. Questo aggiornamento consente agli amministratori di controllare l'aspetto del client e di scegliere se mantenere l'esperienza client di Lync 2013 o utilizzare la migliore esperienza client Skype for business. Il client Skype for business ha effettivamente sostituito il client Lync 2013 e ha aggiunto la possibilità per gli amministratori di scegliere tra l'esperienza client Lync esistente e la nuova esperienza client Skype for business. Per informazioni su questo aggiornamento, vedere [14 aprile 2015 Update for Lync 2013 (Skype for business) (KB2889923)](https://support.microsoft.com/kb/2889923/).
  
Il 12 maggio 2015 ci sarà un altro aggiornamento mensile da Office che include il client Skype for business aggiornato. Molti clienti che non hanno applicato l'aggiornamento di aprile riprenderanno l'aggiornamento del 12 maggio per Office 2013. Le informazioni contenute in questo argomento consentiranno di preparare l'organizzazione, l'ambiente e gli utenti per l'aggiornamento client. Per semplificare la transizione per gli utenti e i team di supporto, utilizzare le informazioni contenute in questo argomento per facilitare la scelta dell'esperienza client desiderata per gli utenti e quindi apportare le modifiche all'ambiente prima di distribuire l'aggiornamento client nell'organizzazione.
  
- [Quale esperienza client si desidera per gli utenti?](user-experience.md#clientexperience)
    
- [Preparare l'ambiente per il client Skype for business](user-experience.md#usinglync)
    
- [Risorse utili per preparare i team di supporto e gli utenti finali per l'aggiornamento](user-experience.md#support)
    
> [!NOTE]
> L'esperienza client di Lync 2013 non è un'opzione per le versioni client di Skype for business 2016. Prima di tentare di configurare l'ambiente client per l'utilizzo del client Lync 2013, controllare la versione client per verificare che non venga avviata con il numero 16. ad esempio: 16. x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Quale esperienza client si desidera per gli utenti?
<a name="clientexperience"> </a>

Con il nuovo client Skype for business, è possibile controllare l'esperienza client che gli utenti ricevono, Lync o Skype for business. L'esperienza client predefinita dipende dal fatto che si utilizzi Lync o Skype for business locale o online. Se si utilizza Skype for business online (Lync Online) oggi con Microsoft 365 Apps for Enterprise, Microsoft 365 business standard o Office 2013, l'esperienza client Skype for business aggiornata, ispirata all'aspetto di Skype, sarà l'esperienza utente predefinita. Se si utilizza Lync Server in locale oggi, l'esperienza client di Lync sarà l'impostazione predefinita.
  
È possibile configurare l'esperienza client che gli utenti ottengono utilizzando i criteri client. Un criterio client è un insieme di impostazioni di configurazione che vengono applicate agli utenti quando si effettuano l'accesso a Lync o Skype for business.
  
### <a name="skype-for-business-client-experience"></a>Esperienza client Skype for business

Oltre a tutte le funzionalità di Lync, Skype for business offre nuove funzionalità con controlli semplificati e icone familiari di Skype. Alcune nuove funzionalità di Skype for business sono disponibili solo con la nuova esperienza client Skype for business. Per ulteriori informazioni sulle nuove funzionalità di Skype for business, vedere [Discover Skype for business](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Esperienza client Lync

L'esperienza client di Lync è molto simile all'esperienza client Lync 2013 che gli utenti hanno già familiarità con, ma ci sono alcune modifiche che si desidera consentire agli utenti di sapere. Per sapere quali sono le differenze tra l'esperienza client di Lync e il client Lync 2013, vedere [perché viene visualizzato Skype for business quando si utilizza Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) e i collegamenti aggiuntivi più avanti in questo argomento.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Preparare l'ambiente per il client Skype for business
<a name="usinglync"> </a>

Per preparare l'ambiente per l'aggiornamento client, è necessario eseguire alcune operazioni. Prima di iniziare a apportare le modifiche necessarie per configurare l'esperienza client, è innanzitutto necessario assicurarsi di utilizzare una versione di Skype for Business Server o Lync Server che supporta le impostazioni dei criteri client.
  
Dopo aver confermato che si sta utilizzando una versione di Skype for Business Server o Lync Server che supporta le impostazioni dei criteri per controllare l'esperienza client, è necessario configurare le impostazioni dei criteri nell'ambiente. I passaggi specifici che è necessario seguire dipendono dalla versione di Skype for Business Server o Lync Server in uso e dal fatto che gli utenti siano online o in locale. 
  
Sarà necessario apportare queste modifiche prima che l'aggiornamento del client venga recapitato agli utenti, in modo da poter controllare l'esperienza del client dal primo avvio del client Skype for business. Nelle tabelle seguenti vengono illustrati i passaggi da eseguire per configurare l'ambiente per l'esperienza client desiderata per gli utenti.
  
|**Distribuzione**|**Esperienza client Skype for business**|**Esperienza client Lync**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |Non sono disponibili ulteriori passaggi per la distribuzione del client Build 4711,1002 (aprile, 2015) o versioni successive.  <br/> |[Utilizzo di Lync Client Experience con Skype for business online](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |Non sono disponibili ulteriori passaggi per la distribuzione del client Build 4711,1002 (aprile, 2015) o versioni successive.  <br/> |[Utilizzo dell'esperienza client di Lync con Skype for Business Server locale](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 e Lync Server 2010  <br/> |[Utilizzare l'esperienza client Skype con Lync Server 2013 o Lync Server 2010 in locale](user-experience.md#SkypewithLynconprem) <br/> |[Utilizzo di Lync client experience with Lync Server 2013 o Lync Server 2010 locale](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utilizzare l'esperienza client Skype con Lync Server 2013 o Lync Server 2010 in locale
<a name="SkypewithLynconprem"> </a>

Seguire la procedura descritta in questa sezione se si desidera configurare l'esperienza client Skype in una distribuzione locale. L'esperienza predefinita per i locali
  
 **Passaggio 1:** Verificare innanzitutto che sia in esecuzione una versione di Lync Server che supporta le impostazioni dei criteri client.
  
- **Lync server 2013** : è necessario eseguire l'aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) per lync Server 2013 o un aggiornamento successivo. Per informazioni, vedere [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync server 2010** : è necessario eseguire l'aggiornamento cumulativo di febbraio 2015 (4.0.7577.710) per lync Server 2010 o un aggiornamento successivo. Per informazioni, vedere [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Passaggio 2:** Successivamente, utilizzare un criterio client per impostare l'esperienza del client Skype con il client Skype for business. Sono disponibili **tre opzioni** per l'utilizzo di un criterio client per impostare l'esperienza client.
  
  **Opzione 1:** Impostare l'esperienza del client Skype utilizzando un criterio globale. Si noti che il criterio globale si applica a tutti gli utenti nella distribuzione, ma i criteri a livello di utente e di sito hanno la precedenza sui criteri globali:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Opzione 2:** Modificare un criterio client esistente che si sta utilizzando nell'ambiente per includere l'impostazione per abilitare l'esperienza del client Skype. In questo modo è possibile assegnare l'esperienza client Skype solo agli utenti a cui è assegnato il criterio esistente:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Opzione 3:** Creare un nuovo criterio da assegnare agli utenti che includono l'impostazione per l'utilizzo del client Skype. Innanzitutto, creare il nuovo criterio client e specificare il nome del criterio come valore del parametro **Identity** :
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Assegnare quindi il criterio agli utenti, utilizzando il nome del criterio, ovvero il valore utilizzato per il parametro **Identity** , come valore del parametro **PolicyName** :
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Passaggio 3:** Dopo aver configurato i criteri client, distribuire il client Skype for business, Build 4711,1002 (aprile, 2015) o versione successiva.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utilizzo di Lync client experience with Lync Server 2013 o Lync Server 2010 locale
<a name="LyncwithLynconprem"> </a>

Questa è l'esperienza predefinita quando il client Skype for business viene distribuito in una distribuzione di Lync Server locale. Non è necessario configurare i criteri client in modo che utilizzino l'esperienza client di Lync, ma è possibile controllare il comportamento del primo esecuzione per il client. Per impostazione predefinita, la prima volta che gli utenti avviano il client Skype for business, viene utilizzata l'esperienza client Skype e viene visualizzata una notifica agli utenti che richiede di riavviare il client per ottenere l'esperienza client di Lync. È possibile configurare l'ambiente in modo che l'esperienza client Lync venga visualizzata al primo avvio del client, nonché disattivare l'esercitazione del client modificando il registro di sistema nei computer client. Per i passaggi che è necessario eseguire prima di distribuire il client Skype for business, vedere uno dei seguenti argomenti:
  
- **Lync server 2013**, vedere [Configure the client experience with Skype for business in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync server 2010** vedere [Configure the client experience with Skype for business in Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Utilizzo dell'esperienza client di Lync con Skype for Business Server locale
<a name="LyncwithSfBServer"> </a>

Attenersi alla procedura descritta in questa sezione se si desidera configurare l'esperienza client Lync in una distribuzione di Skype for Business Server locale.
  
Seguire la procedura descritta in questa sezione se si desidera configurare l'esperienza client Skype in una distribuzione locale. L'esperienza predefinita per i locali
  
 **Passaggio 1:** Per prima cosa, distribuire Skype for Business Server.
  
 **Passaggio 2:** Successivamente, utilizzare un criterio client per impostare l'esperienza client di Lync con il client Skype for business. Sono disponibili **tre opzioni** per l'utilizzo di un criterio client per impostare l'esperienza client.
  
 **Opzione 1:** Impostare l'esperienza client di Lync utilizzando un criterio globale. Si noti che il criterio globale si applica a tutti gli utenti nella distribuzione, ma i criteri a livello di utente e di sito hanno la precedenza sui criteri globali:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Opzione 2:** Modificare un criterio client esistente che si sta utilizzando nell'ambiente per includere l'impostazione per abilitare l'esperienza client Lync. In questo modo è possibile assegnare l'esperienza client di Lync solo agli utenti a cui è assegnato il criterio esistente:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Opzione 3:** Creare un nuovo criterio da assegnare agli utenti che includono l'impostazione per l'utilizzo del client Lync. Innanzitutto, creare il nuovo criterio client e specificare il nome del criterio come valore del parametro **Identity** :
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Assegnare quindi il criterio agli utenti, utilizzando il nome del criterio, ovvero il valore utilizzato per il parametro **Identity** , come valore del parametro **PolicyName** :
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Passaggio 3: facoltativo** -per impostazione predefinita, la prima volta che gli utenti avviano il client Skype for business, viene utilizzata l'esperienza client Skype e viene visualizzata una notifica agli utenti che chiedono di riavviare il client per ottenere l'esperienza client di Lync. È possibile configurare l'ambiente in modo che l'esperienza client di Lync venga visualizzata al primo avvio del client, nonché disattivare l'esercitazione del client, modificando il registro di sistema nei computer client. Per i passaggi che è necessario eseguire prima di distribuire il client Skype for business, vedere [Configure the client experience with Skype for business](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Passaggio 4:** Dopo aver configurato i criteri client, distribuire il client Skype for business, Build 4711,1002 (aprile, 2015) o versione successiva.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Utilizzo di Lync Client Experience con Skype for business online
<a name="LyncwithSfBO"> </a>

Seguire la procedura descritta in questa sezione se si desidera configurare l'esperienza client di Lync e l'utente utilizzando Skype for business online.
  
Se si utilizza Skype for business online, è comunque possibile utilizzare l'esperienza client di Lync con il client Skype for business nell'organizzazione tramite Remote PowerShell per configurare i criteri client. Sono disponibili **tre opzioni** per l'utilizzo di un criterio client per impostare l'esperienza client. Si noti che i criteri e i nomi dei parametri sono diversi dalle impostazioni utilizzate per configurare l'esperienza client quando si utilizza Skype for business o Lync Server locale.
  
 **Opzione 1:** Impostare l'esperienza client di Lync utilizzando un criterio globale. Si noti che i criteri per i client e i siti applicati agli utenti avranno la precedenza su un criterio globale.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opzione 2:** Modificare un criterio client esistente che si sta utilizzando nell'ambiente per includere l'impostazione per abilitare l'esperienza client Lync. In questo modo è possibile assegnare l'esperienza client di Lync solo agli utenti a cui è assegnato il criterio esistente:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opzione 3:** Utilizzare un'istanza di criteri personalizzata che includa l'impostazione per l'utilizzo del client Lync.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Dopo aver configurato i criteri client, distribuire il client Skype for business, Build 4711,1002 (aprile, 2015) o versione successiva.
  
Per informazioni dettagliate su come configurare l'esperienza client con Skype for business online, inclusi i passaggi su come controllare la prima esperienza di esecuzione e gli script di PowerShell che è possibile utilizzare per configurare l'ambiente, vedere [commutazione tra le interfacce utente di Skype for business e Lync client](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Risorse utili per preparare i team di supporto e gli utenti finali per l'aggiornamento
<a name="support"> </a>

Per semplificare la preparazione e l'organizzazione per la transizione, sono disponibili molte risorse aggiuntive che consentono di pianificare, informare e coinvolgere gli utenti finali.
  
- [Video: Presentazione di Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Guide introduttive di Skype for business (download)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync è ora Skype for Business-vedere What ' s New](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for business: Guida dettagliata per i nuovi utenti](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Perché viene visualizzato Skype for business quando si utilizza Lync?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

