# SSO Implementation

## Install npm
    npm install ht_record
    or
    import { Record } from "../../../../DLSE/src/app/service/Record";

## Place in service or app component and call init()
    
    record: any;
    record_init() {
        this.record = new Record(environment.url.apiUrl, environment.url.assetsPortal, environment.url.token);
        let user = this.record.init({
        title: document.title,
        url: location.origin,
        // debug: true 
        });
        user.then((data: any) => {
        console.log(data);
        this.user.name = data.name;
        this.user.email = data.email;
        if (location.origin.indexOf('localhost') == -1)
            this.record_send_status('page_log', 'ACCESSED')
        })
    }

    record_send_status(key: string, val: string) {
        if (this.user.name != "" && this.user.email != "")
        this.record.send(this.user.name, this.user.email, key, val);
    }