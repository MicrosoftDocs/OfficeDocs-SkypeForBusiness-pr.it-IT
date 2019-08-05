---
title: Gestire le applicazioni attendibili
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK, considerato attendibile da Skype for Business Server.
ms.openlocfilehash: 272785cd1dcfe0bf21f7ac2b5ab64f36646237eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187073"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gestire le applicazioni attendibili in Skype for Business Server

Un' *applicazione attendibile* è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK, considerato attendibile da Skype for Business Server. Per informazioni dettagliate sulle applicazioni di UCMA, vedere "documentazione su Unified Communications Managed API 3,0 Core http://go.microsoft.com/fwlink/p/?linkId=210320SDK" at.

Per pubblicare, abilitare o disabilitare correttamente una topologia durante l'aggiunta o la rimozione di un ruolo del server, è necessario essere connessi come utenti membri dei gruppi RTCUniversalServerAdmins e Domain Admins. 

Per informazioni su come configurare un nuovo server applicazioni attendibile, vedere un elenco di applicazioni attendibili e visualizzare le informazioni attendibili sull'applicazione. 

## <a name="configure-a-new-trusted-application-server"></a>Configurare un nuovo server applicazioni attendibile

1.  Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Skype for Business Server**e quindi fare clic su **Generatore di topologia di Skype for Business Server**.

3.  Selezionare **Scarica topologia da distribuzione esistente**e quindi fare clic su **OK**.

4.  Nella finestra di dialogo **Salva topologia con nome** fare clic sul file di generatore di topologia che si vuole usare e quindi fare clic su **Salva**.

5.  Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili**e quindi scegliere **nuovo pool di applicazioni attendibili**.

6.  Immettere il **nome di dominio completo del pool** di applicazioni attendibili, selezionare se si tratta di un server singolo o di più server e quindi fare clic su **Avanti**.

7.  Nella pagina **selezionare l'hop successivo** , nell'elenco, selezionare il pool Front-End di Skype for Business Server.

8.  Fare clic su **fine**.

9.  Selezionare il nodo superiore di **Skype for Business Server**e quindi, nel menu **azioni** , fare clic su **Pubblica topologia**.
    
    Il **pool di applicazioni attendibili** deve essere stato creato correttamente e associato al pool Front-end corretto.


## <a name="view-a-list-of-trusted-applications"></a>Visualizzare un elenco di applicazioni attendibili

Puoi usare il pannello di controllo di Skype for Business Server per visualizzare un elenco delle applicazioni attendibili distribuite nell'ambiente di Skype for Business Server. Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK, considerato attendibile da Skype for Business Server. Questa relazione di trust viene riepilogata nell'elenco seguente:

  - Le applicazioni attendibili non vengono contestate per l'autenticazione da Skype for Business Server.

  - Le applicazioni attendibili non vengono strozzate da Skype for Business Server per le transazioni SIP, le connessioni o le chiamate VoIP (Voice over Internet Protocol) in uscita.

  - Le applicazioni attendibili possono rappresentare qualsiasi utente e possono partecipare a conferenze senza comparire in roster.

  - Le applicazioni attendibili sono altamente disponibili e resilienti.

Nel pannello di controllo di Skype for Business Server puoi vedere il nome delle applicazioni, il pool in cui vengono eseguite e la porta che usano.


### <a name="to-view-a-list-of-trusted-applications"></a>Per visualizzare un elenco di applicazioni attendibili

1.  Da un account utente assegnato al ruolo CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator, accedere a qualsiasi computer della distribuzione interna. Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Skype for Business Server, vedere [controllo di accesso basato sui ruoli (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3.  Nella barra di spostamento sinistra fare clic **** su topologia e quindi su **applicazione attendibile**.

4.  Nella pagina dell' **applicazione attendibile** fare clic su un'intestazione di colonna per ordinare le applicazioni, se necessario.


## <a name="view-trusted-application-information"></a>Visualizzare le informazioni sull'applicazione attendibili

Per visualizzare informazioni sulle applicazioni attendibili, è possibile usare Windows PowerShell e il cmdlet **Get-CsTrustedApplication** . Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Per visualizzare le applicazioni attendibili

Per visualizzare tutte le applicazioni attendibili, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsConferenceDisclaimer
    
   Questo comando restituisce informazioni simili a quelle seguenti per ogni applicazione attendibile:
    
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
    
   Per informazioni dettagliate, vedere [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
