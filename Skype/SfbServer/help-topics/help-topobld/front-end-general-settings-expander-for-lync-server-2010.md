---
title: Espansione delle impostazioni generali di Front End Server per Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'È possibile modificare le proprietà del Front End Server o del pool Front End modificando o configurando gli attributi seguenti. La pagina di configurazione è suddivisa nelle sezioni seguenti:'
ms.openlocfilehash: c0174d6a0badadc217119b5b2ea1028bc01367278739d5b6b03bb4ae83c0f21d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315762"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni generali di Front End per Lync Server 2010

È possibile modificare le proprietà del Front End Server o del pool Front End modificando o configurando gli attributi seguenti. La pagina di configurazione è suddivisa nelle sezioni seguenti:

 **Generale**

- **FQDN**: nome di dominio completo del Front End Server o del pool Front End.

- Selezionare **Usa tutti gli indirizzi IP configurati** per utilizzare tutti gli indirizzi configurati nel Front End Server o nel pool Front End.

    > [!IMPORTANT]
    > Non selezionare questa opzione se si colloca il Mediation Server nel Front End Server o nel pool Front End. Mediation Server e Front End Server necessitano di indirizzi IP dedicati su cui comunicare.

- Selezionare **Limita l'utilizzo del** servizio agli indirizzi IP selezionati e immettere l'indirizzo IP per l'indirizzo **IP** primario per la comunicazione del Front End Server o del pool Front End con il resto della distribuzione. Digitare in **Indirizzo IP PSTN** l'indirizzo IP associato al Mediation Server.

    **Caratteristiche e funzionalità**

- **Servizio di conferenza**: selezionare la casella di controllo per aggiungere funzionalità di conferenza alla distribuzione. Queste funzionalità includono audio, video, condivisione di applicazioni, condivisione desktop e conferenze Web. Sarà necessario creare e associare un Office Web Apps Server per conferenze Web (definito più avanti in questa pagina Proprietà).

- Se si è selezionato Servizio di conferenza, è possibile selezionare la casella di controllo **Servizi di conferenza telefonica con accesso esterno (PSTN)** per abilitare le funzionalità di conferenza telefonica con accesso esterno.

- Selezionare la casella di controllo **VoIP aziendale** se si desidera distribuire funzionalità per consentire a Lync Server 2013 di agire come sistema vocale telefonico utilizzando tecnologie VoIP (Voice over IP), inclusa la possibilità di distribuire telefoni del ricevitore, trunk SIP o connettività di rete telefonica a commutazione pubblica utilizzando Mediation Server, gateway PSTN e IP-PBX, in combinazione o da soli, in base alla progettazione e ai requisiti. Per informazioni dettagliate VoIP aziendale, vedere [VoIP aziendale](/previous-versions/office/lync-server-2013/lync-server-2013-enterprise-voice) e [Plan for VoIP aziendale in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Associazioni**

- **SQL Server archivio**: FQDN del SQL Server (e facoltativamente un'istanza denominata) associato al Front End Server o al pool Front End. È possibile selezionare l'archivio SQL Server nell'elenco o crearne uno nuovo facendo clic su **Nuovo**

- **Archivio file:** selezionare il nome di dominio completo del server e la condivisione (nel formato ) che fungerà da percorso di archiviazione file per i file condivisi creati e utilizzati da Lync Server 2013 per la replica, le directory conferenze e altri  `\\<FQDN of server>\<share name>` scopi. È possibile selezionare l'archivio file nell'elenco o crearne uno nuovo facendo clic su **Nuovo**.

- Selezionare la **casella di controllo Associa server** di archiviazione per abilitare un server di archiviazione per questo Front End Server o pool Front End. Dopo aver selezionato la casella di controllo, selezionare un server di archiviazione esistente nell'elenco o fare clic su **Nuovo** per creare le definizioni per un nuovo server di archiviazione.

- Selezionare la **casella di controllo Associa Monitoring Server** per abilitare un Monitoring Server per questo Front End Server o pool Front End. Dopo aver selezionato la casella di controllo, selezionare un Monitoring Server esistente nell'elenco o fare clic su **Nuovo** per creare le definizioni per un nuovo Monitoring Server.

- Selezionare la casella di controllo Associa pool di server perimetrali **(per** i componenti multimediali) per abilitare un server perimetrale per il Front End Server o il pool Front End. Dopo aver selezionato la casella di controllo, selezionare un server perimetrale o un pool esistente nell'elenco o fare clic **su** Nuovo per creare le definizioni per un nuovo server perimetrale o un nuovo pool.

  **Resilienza**

- Selezionare la casella di controllo Pool di registrazione di **backup** associato per selezionare nell'elenco un Front End Server o un pool Front End che sarà la funzione di registrazione di backup, ovvero il Front End Server o il pool Front End designato come registrar secondario in caso di errore del server primario.

- Se si è selezionata l'opzione Pool di registrazione di backup associato e si è scelta una funzione di registrazione di backup, è possibile selezionare la casella di controllo **Failover e failback automatico per VolP**, in modo da poter definire proprietà numeriche per **Intervallo rilevamento errori VolP (sec)** e **Intervallo failback VolP (sec)**. Per informazioni dettagliate, vedere [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)

  **Servizi Web**

- Per configurare **Servizi Web interni**, è necessario definire **Porte di attesa** per **HTTP** e **HTTPS**. Le porte predefinite sono rispettivamente la porta TCP 80 e la porta TCP 443. È inoltre necessario configurare **Porte pubblicate** per **HTTP** e **HTTPS**. Le porte predefinite sono rispettivamente la porta TCP 80 e la porta TCP 443. Modificare i valori di queste porte a seconda della configurazione dei servizi Web interni e dell'uso dei servizi di bilanciamento del carico (hardware e DNS).

    > [!IMPORTANT]
    > I servizi Web interni e le porte di attesa e pubblicate definite sono riservate ai client e ai dispositivi interni. I client e i dispositivi esterni usano le porte di attesa e pubblicate dei servizi Web esterni, insieme al nome di dominio completo (FQDN) definito per tali servizi.

- Per configurare **Servizi Web esterni**, è necessario definire **Porte di attesa** per **HTTP** e **HTTPS**. Le porte predefinite sono rispettivamente la porta TCP 80 e la porta TCP 443. È inoltre necessario configurare **Porte pubblicate** per **HTTP** e **HTTPS**. Le porte predefinite sono rispettivamente la porta TCP 80 e la porta TCP 443. Modificare i valori di queste porte a seconda della configurazione dei servizi Web interni e dell'uso dei servizi di bilanciamento del carico (hardware e DNS).

    > [!IMPORTANT]
    > I servizi Web esterni e le porte di attesa e pubblicate definite sono riservate ai client e ai dispositivi esterni. I client e i dispositivi esterni usano le porte di attesa e pubblicate dei servizi Web esterni, in genere definite dal proxy inverso insieme al nome di dominio completo (FQDN) definito per tali servizi. La relazione dell'FQDN dei servizi Web esterni e gli URL semplici definiscono gli indirizzi URL (Uniform Resource Locator) che verranno usati dai client esterni per accedere ai servizi disponibili per gli utenti e i dispositivi esterni. Per informazioni dettagliate sugli URL semplici, vedere [Planning for Simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls).

  **Mediation Server**

- Per configurare le **proprietà del Mediation Server** per un Mediation Server collocato, ovvero un Mediation Server distribuito nel Front End Server o nel pool Front End, selezionare Mediation Server **collocato abilitato.**

- Per definire le **porte di attesa** per un Mediation Server collocato, digitare il valore della porta **TLS** e **TCP** su cui è in attesa il Mediation Server collocato. Il valore predefinito di TLS è la porta TCP 5067.

- Per definire un valore di porta TCP per il Mediation Server, selezionare la **casella di controllo Abilita porta TCP.** Per impostazione predefinita, Mediation Server utilizza il protocollo TLS (Transport Layer Security) su TCP. Le porte TCP sono disponibili solo quando l'opzione Abilita la porta TCP è selezionata.

    > [!NOTE]
    > Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile consultare i requisiti del gateway o della rete PSTN in uso. Il valore predefinito della porta TCP è 5068.

- È necessario definire i trunk associati al Mediation Server collocato. Se sono già stati definiti, i trunk potranno essere associati al Mediation Server.

    Se a un Mediation Server sono associati più gateway, è possibile specificare il gateway predefinito selezionando il gateway che si desidera impostare come predefinito e facendo clic su **Rendi predefinito**. Se si vuole rimuovere il gateway predefinito corrente, selezionarlo e fare clic su **Annulla predefinito**.

> [!IMPORTANT]
> Se si apportano modifiche alle proprietà in questa finestra di dialogo, è necessario pubblicare la topologia ed eseguire la distribuzione guidata di Skype for Business Server in tutti i server interessati. Dopo la pubblicazione della nuova topologia, viene fornito un elenco dei server interessati in cui deve essere eseguita la Distribuzione guidata di Skype for Business Server come collegamento nella schermata di riepilogo della pubblicazione della topologia completata. Per informazioni dettagliate sulla pubblicazione della topologia aggiornata, vedere [Publish the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-topology). Per informazioni dettagliate sulla Skype for Business Server guidata, vedere [Strumenti di amministrazione di Lync Server.](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-administrative-tools)

Fare clic su **OK** per salvare le modifiche al documento della topologia.

Fare **clic su** Annulla per ignorare le modifiche e chiudere la finestra **di** dialogo Modifica proprietà per il Front End Server o il pool Front End.

Fare clic su **?** per leggere questo argomento della Guida.

## <a name="see-also"></a>Vedere anche

[Definire e configurare un pool Front End o un server Standard Edition](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)