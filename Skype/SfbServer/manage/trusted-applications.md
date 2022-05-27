---
title: Gestire applicazioni attendibili
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK considerato attendibile da Skype for Business Server.
ms.openlocfilehash: 909ade1fbb44410d6b2acb695b8111e43d766e50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674538"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gestire applicazioni attendibili in Skype for Business Server

*Un'applicazione attendibile* è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK considerato attendibile da Skype for Business Server. Per informazioni dettagliate sulle applicazioni UCMA, vedere "Unified Communications Managed API 3.0 Core SDK Documentation" all'indirizzo https://go.microsoft.com/fwlink/p/?linkId=210320.

Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo del server, è necessario aver eseguito l'accesso come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins. 

Usare questo articolo per informazioni su come configurare un nuovo server applicazioni attendibile, visualizzare un elenco di applicazioni attendibili e visualizzare informazioni sulle applicazioni attendibili. 

## <a name="configure-a-new-trusted-application-server"></a>Configurare un nuovo server applicazioni attendibile

1.  Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Avvia Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Skype for Business Server** e quindi fare clic su **Skype for Business Server Generatore di topologie**.

3.  Selezionare **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **OK**.

4.  Nella finestra di dialogo **Salva topologia con** nome fare clic sul file di Generatore di topologie che si vuole usare e quindi fare clic su **Salva**.

5.  Nel riquadro sinistro fare clic con il pulsante destro del mouse su **Server applicazioni attendibili** e quindi scegliere **Nuovo pool di applicazioni attendibili**.

6.  Immettere il valore di **FQDN pool** per il pool di applicazioni attendibili, specificare se sarà un pool a server singolo o a più server e quindi fare clic su **Avanti**.

7.  Nella pagina **Selezionare l'hop successivo** selezionare l'Skype for Business Server pool Front End dall'elenco.

8.  Fare clic su **Fine**.

9.  Selezionare il nodo superiore **Skype for Business Server** e quindi scegliere **Pubblica topologia** dal menu **Azioni**.
    
    Il **pool di applicazioni attendibili** deve essere stato creato correttamente e associato al pool Front End corretto.


## <a name="view-a-list-of-trusted-applications"></a>Visualizzare un elenco di applicazioni attendibili

È possibile usare il Skype for Business Server Pannello di controllo per visualizzare un elenco delle applicazioni attendibili distribuite nell'ambiente Skype for Business Server. Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK considerato attendibile da Skype for Business Server. Questa relazione di trust è riepilogata nell'elenco seguente:

  - Le applicazioni attendibili non vengono richieste per l'autenticazione da Skype for Business Server.

  - Le applicazioni attendibili non vengono limitate da Skype for Business Server per le transazioni SIP, le connessioni o le chiamate VoIP (Voice over Internet Protocol) in uscita.

  - Le applicazioni attendibili possono rappresentare qualsiasi utente e possono partecipare a conferenze senza essere inserite negli elenchi dei partecipanti.

  - Le applicazioni attendibili sono resilienti e a disponibilità elevata.

Nel Skype for Business Server Pannello di controllo è possibile visualizzare il nome delle applicazioni, il pool in cui vengono eseguite e la porta usata.


### <a name="to-view-a-list-of-trusted-applications"></a>Per visualizzare un elenco di applicazioni attendibili

1.  Da un account utente assegnato al ruolo CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator, accedere a un computer nella distribuzione interna. Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Skype for Business Server, vedere [Controllo degli accessi in base al](../plan-your-deployment/security/role-based-access-control-rbac.md) ruolo.

2.  Aprire una finestra del browser e quindi immettere l'URL Amministrazione per aprire il Skype for Business Server Pannello di controllo.

3.  Nella barra di spostamento a sinistra fare clic su **Topologia** e quindi su **Applicazione attendibile**.

4.  Nella pagina **Applicazione attendibile** fare clic sull'intestazione di una colonna per ordinare le applicazioni, se necessario.


## <a name="view-trusted-application-information"></a>Visualizzare le informazioni sulle applicazioni attendibili

È possibile visualizzare informazioni sulle applicazioni attendibili usando Windows PowerShell e il cmdlet **Get-CsTrustedApplication**. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Per visualizzare le applicazioni affidabili

Per visualizzare tutte le applicazioni attendibili, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
   **Get-CsConferenceDisclaimer**
    
   Il comando restituisce informazioni simili a questa, per ciascuna applicazione affidabile:
    
   Identità: CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com<br/>
   RegistrarPool: 487279971<br/>
   HomeServer : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com OwnerUrn : urn:application:helpdesk<br/>
   SipAddress : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   Displayname:<br/>
   DisplayNumber :<br/>
   Lineuri:<br/>
   PrimaryLanguage : 0<br/>
   SecondaryLanguages : {}<br/>
   EnterpriseVoiceEnabled: True<br/>
   ExUmEnabled: False<br/>
   Abilitato: True<br/>
    
   For details, see [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).