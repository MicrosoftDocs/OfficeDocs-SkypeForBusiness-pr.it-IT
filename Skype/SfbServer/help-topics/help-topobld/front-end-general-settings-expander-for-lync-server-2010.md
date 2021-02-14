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
ms.openlocfilehash: 8616d65a73f1fb618a72ab41bc628527aa6e2a59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818396"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni generali di Front End per Lync Server 2010

È possibile modificare le proprietà del Front End Server o del pool Front End modificando o configurando gli attributi seguenti. La pagina di configurazione è suddivisa nelle sezioni seguenti:

 **Generale**

- **FQDN:** il nome di dominio completo del Front End Server o del pool Front End.

- Selezionare **Usa tutti gli indirizzi IP configurati** per utilizzare tutti gli indirizzi configurati nel Front End Server o nel pool Front End.

    > [!IMPORTANT]
    > Non selezionare questa opzione se si colloca il Mediation Server nel Front End Server o nel pool Front End. I Mediation Server e i Front End Server necessitano di indirizzi IP dedicati in cui comunicare.

- Selezionare **Limita utilizzo servizio a** indirizzi IP selezionati e immettere l'indirizzo IP per l'indirizzo **IP** primario per la comunicazione del Front End Server o del pool Front End con il resto della distribuzione. Digitare **nell'indirizzo IP PSTN** l'indirizzo IP associato al Mediation Server.

    **Caratteristiche e funzionalità**

- **Servizio di conferenza**: selezionare la casella di controllo per aggiungere funzionalità di conferenza alla distribuzione. Queste funzionalità includono audio, video, condivisione di applicazioni, condivisione desktop e conferenze Web. Sarà necessario creare e associare un server Office Web Apps per conferenze Web (definito più avanti in questa pagina delle proprietà).

- Se è stata selezionata l'opzione Servizio di conferenza telefonica, è possibile selezionare Le conferenze telefoniche con accesso esterno **(PSTN).** Selezionare la casella di controllo per abilitare le funzionalità di conferenza telefonica con accesso esterno.

- Selezionare la casella di controllo **VoIP aziendale** se si intende distribuire funzionalità per consentire a Lync Server 2013 di agire come sistema vocale telefonico utilizzando tecnologie VoIP (Voice over IP), inclusa la possibilità di distribuire telefoni ricevitori, trunk SIP o connettività di rete telefonica a commutazione pubblica utilizzando Mediation Server, gateway PSTN e IP-PBX, in combinazione o da soli, in base alla progettazione e ai requisiti. Per informazioni dettagliate VoIP aziendale, vedere [VoIP aziendale](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) e [Pianificare VoIP aziendale in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Associazioni**

- **SQL Server:** il nome di dominio completo del SQL Server (e facoltativamente un'istanza denominata) associato al Front End Server o al pool Front End. È possibile selezionare l'archivio SQL Server nell'elenco o crearne uno nuovo facendo clic su **Nuovo**

- **Archivio** file: selezionare il nome di dominio completo del server e la condivisione (nel formato ) che fungerà da percorso di archivio file per i file condivisi creati e utilizzati da Lync Server 2013 per la replica, le directory conferenze e altri  `\\<FQDN of server>\<share name>` scopi. È possibile selezionare l'archivio file nell'elenco o crearne uno nuovo facendo clic su **Nuovo**.

- Selezionare la **casella di controllo Associa server** di archiviazione per abilitare un server di archiviazione per il Front End Server o il pool Front End. Dopo aver selezionato la casella di controllo, selezionare  un server di archiviazione esistente nell'elenco o fare clic su Nuovo per creare le definizioni per un nuovo server di archiviazione.

- Selezionare la **casella di controllo Associa Monitoring Server** per abilitare un Monitoring Server per questo Front End Server o pool Front End. Dopo aver selezionato la casella di controllo, selezionare  un Monitoring Server esistente nell'elenco o fare clic su Nuovo per creare le definizioni per un nuovo Monitoring Server.

- Selezionare la casella di controllo Associa pool di server perimetrali **(per** i componenti multimediali) per abilitare un server perimetrale per il Front End Server o il pool Front End. Dopo aver selezionato la casella di controllo, selezionare un  server perimetrale o un pool di server perimetrali esistente nell'elenco o fare clic su Nuovo per creare le definizioni per un nuovo server perimetrale o un nuovo pool.

  **Resilienza**

- Selezionare la casella di controllo Pool di registrazione di **backup** associato per selezionare nell'elenco un Front End Server o un pool Front End che sarà il servizio di registrazione di backup, ovvero il Front End Server o il pool Front End designato come registrar secondario in caso di errore del server principale.

- Se è stato selezionato Pool di registrazione di backup associato ed è stato scelto un registrar di backup, è possibile selezionare la casella di controllo failover e failback automatici **per Voice.** È ora possibile definire le proprietà numeriche per il rilevamento del failover vocale **interno (sec)** e l'intervallo **di failback vocale (sec).** Per informazioni dettagliate, vedere [Planning for VoIP aziendale Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Servizi Web**

- Per configurare **Servizi Web interni**, è necessario definire **Porte di attesa** per **HTTP** e **HTTPS**. Le porte predefinite sono rispettivamente la porta TCP 80 e la porta TCP 443. È inoltre necessario configurare **Porte pubblicate** per **HTTP** e **HTTPS**. Le porte predefinite sono rispettivamente la porta TCP 80 e la porta TCP 443. Modificare i valori di queste porte a seconda della configurazione dei servizi Web interni e dell'uso dei servizi di bilanciamento del carico (hardware e DNS).

    > [!IMPORTANT]
    > I servizi Web interni e le porte di attesa e pubblicate definite sono riservate ai client e ai dispositivi interni. I client e i dispositivi esterni usano le porte di attesa e pubblicate dei servizi Web esterni, insieme al nome di dominio completo (FQDN) definito per tali servizi.

- Per configurare **Servizi Web esterni**, è necessario definire **Porte di attesa** per **HTTP** e **HTTPS**. Le porte predefinite sono rispettivamente la porta TCP 80 e la porta TCP 443. È inoltre necessario configurare **Porte pubblicate** per **HTTP** e **HTTPS**. Le porte predefinite sono rispettivamente la porta TCP 80 e la porta TCP 443. Modificare i valori di queste porte a seconda della configurazione dei servizi Web interni e dell'uso dei servizi di bilanciamento del carico (hardware e DNS).

    > [!IMPORTANT]
    > I servizi Web esterni e le porte di attesa e pubblicate definite sono riservate ai client e ai dispositivi esterni. I client e i dispositivi esterni usano le porte di attesa e pubblicate dei servizi Web esterni, in genere definite dal proxy inverso insieme al nome di dominio completo (FQDN) definito per tali servizi. La relazione dell'FQDN dei servizi Web esterni e gli URL semplici definiscono gli indirizzi URL (Uniform Resource Locator) che verranno usati dai client esterni per accedere ai servizi disponibili per gli utenti e i dispositivi esterni. Per informazioni dettagliate sugli URL semplici, vedere [Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Mediation Server**

- Per configurare le proprietà **del Mediation Server** per un Mediation Server collocato, ovvero un Mediation Server distribuito nel Front End Server o nel pool Front End, selezionare Mediation Server collocato **abilitato.**

- Per definire le porte **di attesa** per un Mediation Server collocato, digitare il valore delle porte **TLS** e **TCP** su cui il Mediation Server collocato è in attesa. Il valore predefinito di TLS è la porta TCP 5067.

- Per definire un valore di porta TCP per il Mediation Server, selezionare la casella di controllo **Abilita porta TCP.** Per impostazione predefinita, il Mediation Server utilizza il protocollo TLS (Transport Layer Security) su TCP. Le porte TCP sono disponibili solo quando l'opzione Abilita la porta TCP è selezionata.

    > [!NOTE]
    > Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile consultare i requisiti del gateway o della rete PSTN in uso. Il valore predefinito della porta TCP è 5068.

- È necessario definire i trunk associati al Mediation Server collocato. Se sono già stati definiti, i trunk potranno essere associati al Mediation Server.

    Se a un Mediation Server sono associati più gateway, è possibile specificare il gateway predefinito selezionando il gateway che si desidera impostare come predefinito e facendo clic su **Rendi predefinito.** Se si vuole rimuovere il gateway predefinito corrente, selezionarlo e fare clic su **Annulla predefinito**.

> [!IMPORTANT]
> Se si apportano modifiche alle proprietà in questa finestra di dialogo, è necessario pubblicare la topologia ed eseguire la Distribuzione guidata di Skype for Business Server in tutti i server interessati. Dopo aver pubblicato la nuova topologia, viene fornito un elenco dei server interessati in cui deve essere eseguita la Distribuzione guidata di Skype for Business Server come collegamento nella schermata di riepilogo della pubblicazione della topologia corretta. Per informazioni dettagliate sulla pubblicazione della topologia aggiornata, vedere [Publish the Topology](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Per informazioni dettagliate sulla Distribuzione guidata di Skype for Business Server, vedere [Strumenti di amministrazione di Lync Server.](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx)

Fare clic su **OK** per salvare le modifiche al documento della topologia.

Fare **clic su** Annulla per annullare le modifiche e chiudere modifica **proprietà** per il Front End Server o il pool Front End.

Fare clic su **?** per leggere questo argomento della Guida.

## <a name="see-also"></a>Vedere anche

[Definire e configurare un pool Front End o un server Standard Edition](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
