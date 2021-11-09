---
title: Pianificare l'Skype for Business client 2015 per gli utenti
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: "Riepilogo: informazioni sul nuovo Skype for Business e sui passaggi che è possibile eseguire per preparare l'ambiente e gli utenti per l'aggiornamento, Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013 o Lync Server 2010."
ms.openlocfilehash: 9979b7d9fe449de926358097b9fd2fdd36e5afb4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864743"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Pianificare l'Skype for Business client 2015 per gli utenti
 
**Riepilogo:** Informazioni sul nuovo Skype for Business e sui passaggi che è possibile eseguire per preparare l'ambiente e gli utenti per l'aggiornamento, indipendentemente dal fatto che si utilizzi Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013 o Lync Server 2010.
  
Il 14 aprile 2015 Office Update for Lync 2013 include la nuova Skype for Business utente. Questo aggiornamento consente agli amministratori di controllare l'aspetto del client e scegliere se mantenere l'esperienza client di Lync 2013 o utilizzare l'esperienza client Skype for Business client. Il client Skype for Business ha sostituito in modo efficace il client Lync 2013 e ha aggiunto agli amministratori la possibilità di scegliere tra l'esperienza client Lync esistente e la nuova esperienza client Skype for Business client. Per informazioni su questo aggiornamento, vedere Aggiornamento del 14 aprile [2015 per Lync 2013 (Skype for Business) (KB2889923)](https://support.microsoft.com/kb/2889923/).
  
Il 12 maggio 2015 ci sarà un altro aggiornamento mensile da Office che include il client Skype for Business aggiornato. Molti clienti che non hanno applicato l'aggiornamento di aprile riprenderanno l'aggiornamento del 12 maggio Office 2013. Le informazioni contenute in questo argomento consentono di preparare l'organizzazione, l'ambiente e gli utenti per l'aggiornamento del client. Per semplificare la transizione per gli utenti e i team di supporto, utilizzare le informazioni contenute in questo argomento per decidere l'esperienza client desiderata per gli utenti e quindi apportare le modifiche all'ambiente prima di distribuire l'aggiornamento client nell'organizzazione.
  
- [Quale esperienza client si desidera per gli utenti?](user-experience.md#clientexperience)
    
- [Preparare l'ambiente per il client Skype for Business client](user-experience.md#usinglync)
    
- [Risorse per preparare i team di supporto e gli utenti finali per l'aggiornamento](user-experience.md#support)
    
> [!NOTE]
> L'esperienza client lync 2013 non è un'opzione per le Skype for Business client 2016. Prima di tentare di configurare l'ambiente client per l'utilizzo del client Lync 2013, controllare la versione client per assicurarsi che non inizi con il numero 16. ad esempio: 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Quale esperienza client si desidera per gli utenti?
<a name="clientexperience"> </a>

Con il nuovo client Skype for Business, è possibile controllare l'esperienza client che gli utenti ottengono, lync o Skype for Business. L'esperienza client predefinita dipende dal fatto che si utilizzi Lync o Skype for Business locale o online. Se si utilizza Skype for Business Online (Lync Online) oggi con Microsoft 365 Apps for enterprise, Microsoft 365 Business Standard o Office 2013, il Skype for Business l'esperienza client, ispirata all'aspetto Skype, sarà l'esperienza utente predefinita. Se si utilizza Lync Server in locale, l'esperienza client Lync sarà l'impostazione predefinita.
  
È possibile configurare l'esperienza client che gli utenti ottengono utilizzando i criteri client. Un criterio client è un set di impostazioni di configurazione che vengono applicate agli utenti quando eseguono l'accesso a Lync o Skype for Business.
  
### <a name="skype-for-business-client-experience"></a>Skype for Business client

Oltre a tutte le funzionalità di Lync, Skype for Business nuove funzionalità con controlli semplificati e icone familiari di Skype. Alcune nuove funzionalità di Skype for Business sono disponibili solo con la nuova esperienza Skype for Business client. Per ulteriori informazioni sulle nuove funzionalità di Skype for Business, vedere [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Esperienza client Lync

L'esperienza del client Lync è molto simile all'esperienza client lync 2013 che gli utenti hanno già familiarità con, ma esistono alcune modifiche di cui si desidera che gli utenti siano a conoscenza. Per sapere quali sono le differenze tra [l'esperienza](https://go.microsoft.com/fwlink/p/?LinkId=544712) client Lync e il client Lync 2013, vedere Perché viene visualizzato Skype for Business quando si utilizza Lync? e i collegamenti aggiuntivi più avanti in questo argomento.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Preparare l'ambiente per il client Skype for Business client
<a name="usinglync"> </a>

Per prepararsi all'aggiornamento del client, è necessario eseguire alcune operazioni. Prima di iniziare a apportare modifiche per configurare l'esperienza client, è innanzitutto necessario verificare di utilizzare una versione di Skype for Business Server o Lync Server che supporti le impostazioni dei criteri client.
  
Dopo aver confermato di utilizzare una versione di Skype for Business Server o Lync Server che supporta le impostazioni dei criteri per controllare l'esperienza client, sarà necessario configurare le impostazioni dei criteri nell'ambiente. I passaggi specifici da eseguire dipendono dalla versione di Skype for Business Server o Lync Server in uso e dal fatto che gli utenti siano locali o online. 
  
È necessario apportare queste modifiche prima che l'aggiornamento client venga recapitato agli utenti, in modo da poter controllare l'esperienza client dal primo avvio del client Skype for Business client. Nelle tabelle seguenti vengono indicati i passaggi da eseguire per configurare l'ambiente per l'esperienza client desiderata per gli utenti.
  
|**Distribuzione**|**Skype for Business client**|**Esperienza client Lync**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |Non esistono altri passaggi oltre alla distribuzione della build client 4711.1002 (aprile 2015) o successiva.  <br/> |[Usare l'esperienza client Lync con Skype for Business Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |Non esistono altri passaggi oltre alla distribuzione della build client 4711.1002 (aprile 2015) o successiva.  <br/> |[Usare l'esperienza del client Lync Skype for Business Server locale](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 e Lync Server 2010  <br/> |[Utilizzare l Skype client con Lync Server 2013 o Lync Server 2010 locale](user-experience.md#SkypewithLynconprem) <br/> |[Utilizzare l'esperienza client lync con Lync Server 2013 o Lync Server 2010 locale](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utilizzare l Skype client con Lync Server 2013 o Lync Server 2010 locale
<a name="SkypewithLynconprem"> </a>

Seguire i passaggi descritti in questa sezione se si desidera configurare l'Skype client in una distribuzione locale. L'esperienza predefinita per l'ambiente locale
  
 **Passaggio 1:** Verificare innanzitutto di eseguire una versione di Lync Server che supporta le impostazioni dei criteri client.
  
- **Lync Server 2013** - È necessario eseguire l'aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) per Lync Server 2013 o un aggiornamento successivo. Per informazioni, vedere [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** - È necessario eseguire l'aggiornamento cumulativo di febbraio 2015 (4.0.7577.710) per Lync Server 2010 o un aggiornamento successivo. Per informazioni, vedere [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Passaggio 2:** Usa quindi un criterio client per impostare l'Skype client con il client Skype for Business client. Esistono **3 opzioni per** l'utilizzo di un criterio client per impostare l'esperienza client.
  
  **Opzione 1:** Impostare l Skype client utilizzando un criterio globale. Si noti che il criterio globale si applica a tutti gli utenti della distribuzione, ma i criteri a livello di utente e sito hanno la precedenza sul criterio globale:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Opzione 2:** Modificare un criterio client esistente in uso nell'ambiente in modo da includere l'impostazione per abilitare l'Skype client. In questo modo è possibile assegnare Skype client solo agli utenti a cui è assegnato il criterio esistente:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Opzione 3:** Crea un nuovo criterio da assegnare agli utenti che include l'impostazione per l'esperienza Skype client. Creare innanzitutto il nuovo criterio client e specificare il nome del criterio come valore del **parametro Identity:**
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Assegnare quindi il criterio agli utenti, utilizzando il nome del criterio (il valore utilizzato per il parametro **Identity)** come valore del **parametro PolicyName:**
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Passaggio 3:** Dopo aver configurato i criteri client, distribuire il client Skype for Business, compilare 4711.1002 (aprile 2015) o versione successiva.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utilizzare l'esperienza client lync con Lync Server 2013 o Lync Server 2010 locale
<a name="LyncwithLynconprem"> </a>

Questa è l'esperienza predefinita quando il client Skype for Business viene distribuito in una distribuzione di Lync Server locale. Non è necessario configurare criteri client per l'utilizzo dell'esperienza client Lync, ma è possibile controllare il comportamento della prima esecuzione per il client. Per impostazione predefinita, la prima volta che gli utenti avviano il client Skype for Business, viene utilizzata l'esperienza client di Skype e viene visualizzata una notifica agli utenti che richiede di riavviare il client per ottenere l'esperienza client Lync. È possibile configurare l'ambiente in modo che l'esperienza client Lync sia visualizzata la prima volta che gli utenti avviano il client, nonché disattivare l'esercitazione client modificando il Registro di sistema nei computer client. Per i passaggi da eseguire prima di distribuire il client Skype for Business client, vedere uno dei seguenti argomenti:
  
- **Lync Server 2013**, vedere Configurare l'esperienza client con Skype for Business [in Lync Server 2013](/previous-versions/office/lync-server-2013/configure-the-skype-for-business-client-in-lync-server-2013)
    
- **Lync Server 2010 vedere** [Configure the client experience with Skype for Business in Lync Server 2010](/previous-versions/office/skype-server-2010/dn955209(v=ocs.14))
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Usare l'esperienza del client Lync Skype for Business Server locale
<a name="LyncwithSfBServer"> </a>

Seguire i passaggi descritti in questa sezione se si desidera configurare l'esperienza client Lync in una distribuzione Skype for Business Server locale.
  
Seguire i passaggi descritti in questa sezione se si desidera configurare l'Skype client in una distribuzione locale. L'esperienza predefinita per l'ambiente locale
  
 **Passaggio 1:** Innanzitutto, distribuire Skype for Business Server.
  
 **Passaggio 2:** Successivamente, utilizzare un criterio client per impostare l'esperienza del client Lync con il client Skype for Business client. Esistono **3 opzioni per** l'utilizzo di un criterio client per impostare l'esperienza client.
  
 **Opzione 1:** Impostare l'esperienza del client Lync utilizzando un criterio globale. Si noti che il criterio globale si applica a tutti gli utenti della distribuzione, ma i criteri a livello di utente e sito hanno la precedenza sul criterio globale:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Opzione 2:** Modificare un criterio client esistente in uso nell'ambiente in modo da includere l'impostazione per abilitare l'esperienza client Lync. In questo modo è possibile assegnare l'esperienza client Lync solo agli utenti a cui è assegnato il criterio esistente:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Opzione 3:** Creare un nuovo criterio da assegnare agli utenti che include l'impostazione per l'esperienza client Lync. Creare innanzitutto il nuovo criterio client e specificare il nome del criterio come valore del **parametro Identity:**
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Assegnare quindi il criterio agli utenti, utilizzando il nome del criterio (il valore utilizzato per il parametro **Identity)** come valore del **parametro PolicyName:**
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Passaggio 3:** facoltativo - Per impostazione predefinita, la prima volta che gli utenti avviano il client Skype for Business, viene utilizzata l'esperienza client di Skype e viene visualizzata una notifica agli utenti che gli chiedono di riavviare il client per ottenere l'esperienza del client Lync. È possibile configurare l'ambiente in modo che l'esperienza client Lync sia visualizzata la prima volta che gli utenti avviano il client, nonché disattivare l'esercitazione sul client, modificando il Registro di sistema nei computer client. Per i passaggi da eseguire prima di distribuire il client Skype for Business client, vedere [Configure the client experience with Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Passaggio 4:** Dopo aver configurato i criteri client, distribuire il client Skype for Business, compilare 4711.1002 (aprile 2015) o versione successiva.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Usare l'esperienza client Lync con Skype for Business Online
<a name="LyncwithSfBO"> </a>

Seguire i passaggi descritti in questa sezione se si desidera configurare l'esperienza client Lync e si utilizza Skype for Business Online.
  
Se si utilizza Skype for Business Online, è comunque possibile utilizzare l'esperienza client Lync con il client Skype for Business nell'organizzazione utilizzando Remote PowerShell per configurare i criteri client. Esistono **3 opzioni per** l'utilizzo di un criterio client per impostare l'esperienza client. Si noti che i nomi dei criteri e dei parametri sono diversi da quelli utilizzati per configurare l'esperienza client quando si utilizza Skype for Business o Lync Server locale.
  
 **Opzione 1:** Impostare l'esperienza del client Lync utilizzando un criterio globale. Tenere presente che i criteri client e siti applicati agli utenti avranno la precedenza su un criterio globale.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opzione 2:** Modificare un criterio client esistente in uso nell'ambiente in modo da includere l'impostazione per abilitare l'esperienza client Lync. In questo modo è possibile assegnare l'esperienza client Lync solo agli utenti a cui è assegnato il criterio esistente:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opzione 3:** Utilizzare un'istanza dei criteri personalizzata che includa l'impostazione per l'esperienza client Lync.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Dopo aver configurato i criteri client, distribuire il client Skype for Business, compilare 4711.1002 (aprile 2015) o versione successiva.
  
Per informazioni dettagliate su come configurare l'esperienza client con Skype for Business Online, inclusi i passaggi per controllare la prima esperienza di esecuzione e gli script di PowerShell che è possibile utilizzare per configurare l'ambiente, vedere [Switching between the Skype for Business and the Lync client user interfaces](../../../SfbOnline/set-up-skype-for-business-online/switching-the-skype-for-business-and-the-lync-client-user-interfaces.md).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Risorse per preparare i team di supporto e gli utenti finali per l'aggiornamento
<a name="support"> </a>

Per facilitare la preparazione della transizione da parte dell'utente e dell'organizzazione, sono disponibili molte risorse aggiuntive che consentono di pianificare, istruire e coinvolgere gli utenti finali.
  
- [Video: Presentazione di Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Business Guide introduttive (download)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync è ora Skype for Business, vedere le novità](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: guida dettagliata per i nuovi utenti](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Perché viene visualizzato Skype for Business quando si utilizza Lync?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
