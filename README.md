# LBRY / Odysee block lists

This repository is an archive of the block lists applied by LBRY and Odysee on their content. 

## Content analyse

This data has been used and is archived by [Check First](https://checkfirst.network) for its [OSINT investigation on content moderation on Odysee and LBRY](https://checkfirst.network).


## Data structure

Block lists are gathered from 2 sources : LBRY and Odysee. The LBRY is divided into 2 distinct blocklist: iOS and Android. 

### LBRY block list
The JSON data returned by the LBRY API call is presented as follows, composed of two fields: `claim_id` and `tag_name`, a text-field including a short explanation of the reason for the block:

```json
{
    "claim_id": "152a48e20dc6df020b90b6d32e6cfdfdb3eb8e98",
    "tag_name": "dmca"
}
```

### Odysee geo-blocklist
The service used by Odysee is a geo-blocking list retrieved by a call to a private API. This list is a JSON file including the different entries of content to be blocked. 

An entry is categorised either as `livestream` or `video` (our analysis has shown that, despite its naming, the livestream category can actually also include both videos and channels. The video category includes only videos and channels). 

Each entry is structured as follows : 

```json
{
    "00032e45fb7bf206d68d140f74e96edcf8b7ad9b": {
        "countries": [
            {
                "id": "DE",
                "trigger": "Govt of the Federal Republic of Germany",
                "reason": "law",
                "message": "The Interstate Treaty on the Protection of Human Dignity and the Protection of Minors in Broadcasting and in Telemedia states this content is illegal: § 4 Abs. 1 Satz 1 Nr. 3 JMStV"
            }
        ]
    }
}
```



## License

[MIT](https://choosealicense.com/licenses/mit/)
