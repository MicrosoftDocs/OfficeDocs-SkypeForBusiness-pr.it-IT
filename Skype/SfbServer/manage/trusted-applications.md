---
title: Gestire le applicazioni attendibili
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK che è attendibile da Skype for Business Server.
ms.openlocfilehash: c5c1a62440ebb98974cee5771c13cf0e5acc55c7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151226"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gestire le applicazioni attendibili in Skype for Business Server

Un' *applicazione attendibile* è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK che è attendibile da Skype for Business Server. Per informazioni dettagliate sulle applicazioni di UCMA, vedere la documentazione relativa a https://go.microsoft.com/fwlink/p/?linkId=210320Unified Communications Managed API 3,0 Core SDK.

Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo del server, è necessario aver eseguito l'accesso come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins. 

Utilizzare questo articolo per informazioni su come configurare un nuovo server applicazioni attendibili, per visualizzare un elenco di applicazioni attendibili e per visualizzare i dati delle applicazioni attendibili. 

## <a name="configure-a-new-trusted-application-server"></a>Configurare un nuovo server applicazioni attendibile

1.  Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server**e quindi su **Generatore di topologie di Skype for Business Server**.

3.  Selezionare **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **OK**.

4.  Nella finestra di dialogo **Salva topologia con nome** fare clic sul file del generatore di topologie che si desidera utilizzare e quindi fare clic su **Salva**.

5.  Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili**e quindi scegliere **nuovo pool di applicazioni attendibili**.

6.  Immettere il valore di **FQDN pool** per il pool di applicazioni attendibili, specificare se sarà un pool a server singolo o a più server e quindi fare clic su **Avanti**.

7.  Nella pagina **selezionare l'hop successivo** , nell'elenco, selezionare il pool Front End di Skype for Business Server.

8.  Fare clic su **Fine**.

9.  Selezionare il nodo principale **Skype for Business Server**e quindi fare clic su **Pubblica topologia**dal menu **azioni** .
    
    È necessario che il **pool di applicazioni attendibili** sia stato creato correttamente e sia associato al pool Front end corretto.


## <a name="view-a-list-of-trusted-applications"></a>Visualizzare un elenco di applicazioni attendibili

È possibile utilizzare il pannello di controllo di Skype for Business Server per visualizzare un elenco delle applicazioni attendibili distribuite nell'ambiente di Skype for Business Server. Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK che è attendibile da Skype for Business Server. Questa relazione di trust è riepilogata nell'elenco seguente:

  - Le applicazioni attendibili non sono contestate per l'autenticazione da parte di Skype for Business Server.

  - Le applicazioni attendibili non vengono limitate da Skype for Business Server per le transazioni SIP, le connessioni o le chiamate VoIP (Voice over Internet Protocol) in uscita.

  - Le applicazioni attendibili possono rappresentare qualsiasi utente e possono partecipare a conferenze senza essere inserite negli elenchi dei partecipanti.

  - Le applicazioni attendibili sono resilienti e a disponibilità elevata.

Nel pannello di controllo di Skype for Business Server, è possibile visualizzare il nome delle applicazioni, il pool in cui vengono eseguite e la porta utilizzata.


### <a name="to-view-a-list-of-trusted-applications"></a>Per visualizzare un elenco di applicazioni attendibili

1.  Da un account utente assegnato al ruolo CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator, accedere a un computer nella distribuzione interna. Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Skype for Business Server, vedere [Role-Based Access Control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.

3.  Sulla barra di spostamento sinistra fare clic su **topologia**e quindi su **applicazione attendibile**.

4.  Nella pagina **Applicazione attendibile** fare clic sull'intestazione di una colonna per ordinare le applicazioni, se necessario.


## <a name="view-trusted-application-information"></a>Visualizzare le informazioni relative alle applicazioni attendibili

È possibile visualizzare informazioni sulle applicazioni attendibili utilizzando Windows PowerShell e il cmdlet **Get-CsTrustedApplication** . Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Per visualizzare le applicazioni affidabili

Per visualizzare tutte le applicazioni attendibili, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsConferenceDisclaimer
    
   Il comando restituisce informazioni simili a questa, per ciascuna applicazione affidabile:
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
