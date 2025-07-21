IFLd7Lvz7ZNTI2qnCnJz8yiYOABJ4sgg

### 첫 번째
1. Get Events - 일반 이벤트 리스트(전체)
   ```
	https://app.ticketmaster.com/discovery/v2/events.json?apikey={YourOwnAPIKey}
   ```

2. Get Events - 일반 이벤트 리스트에 파라미터 추가
 ```
	https://app.ticketmaster.com/discovery/v2/events.json?keyword=BTS&StartDateTime=&city=Seoul&size=2
```

### 두 번째
1. Get Events in Detail - 일반 리스트에서 나온 값을 더 상세하게 조회
```
	https://app.ticketmaster.com/discovery/v2/events/G5vVZbowl3fyp?apikey={YourOwnAPIKey}
```
```
	https://app.ticketmaster.com/discovery/v2/events/{EventId}
```

<img width="557" height="290" alt="image" src="https://github.com/user-attachments/assets/cd1c6c10-e55a-4232-9565-727d24940737" />

</br>

### 전체 Custom Connector Swagger

```
swagger: '2.0'
info:
  title: TicketMaster
  description: ''
  version: '1.0'
host: app.ticketmaster.com
basePath: /
schemes:
  - https
consumes: []
produces: []
paths:
  /discovery/v2/events.json:
    get:
      responses:
        default:
          description: default
          schema:
            type: object
            properties:
              _embedded:
                type: object
                properties:
                  events:
                    type: array
                    items:
                      type: object
                      properties:
                        name:
                          type: string
                          description: name
                        type:
                          type: string
                          description: type
                        id:
                          type: string
                          description: id
                        test:
                          type: boolean
                          description: test
                        url:
                          type: string
                          description: url
                        locale:
                          type: string
                          description: locale
                        images:
                          type: array
                          items:
                            type: object
                            properties:
                              ratio:
                                type: string
                                description: ratio
                              url:
                                type: string
                                description: url
                              width:
                                type: integer
                                format: int32
                                description: width
                              height:
                                type: integer
                                format: int32
                                description: height
                              fallback:
                                type: boolean
                                description: fallback
                              attribution:
                                type: string
                                description: attribution
                          description: images
                        sales:
                          type: object
                          properties:
                            public:
                              type: object
                              properties:
                                startDateTime:
                                  type: string
                                  description: startDateTime
                                startTBD:
                                  type: boolean
                                  description: startTBD
                                startTBA:
                                  type: boolean
                                  description: startTBA
                                endDateTime:
                                  type: string
                                  description: endDateTime
                              description: public
                            presales:
                              type: array
                              items:
                                type: object
                                properties:
                                  startDateTime:
                                    type: string
                                    description: startDateTime
                                  endDateTime:
                                    type: string
                                    description: endDateTime
                                  name:
                                    type: string
                                    description: name
                              description: presales
                          description: sales
                        dates:
                          type: object
                          properties:
                            start:
                              type: object
                              properties:
                                localDate:
                                  type: string
                                  description: localDate
                                localTime:
                                  type: string
                                  description: localTime
                                dateTime:
                                  type: string
                                  description: dateTime
                                dateTBD:
                                  type: boolean
                                  description: dateTBD
                                dateTBA:
                                  type: boolean
                                  description: dateTBA
                                timeTBA:
                                  type: boolean
                                  description: timeTBA
                                noSpecificTime:
                                  type: boolean
                                  description: noSpecificTime
                              description: start
                            timezone:
                              type: string
                              description: timezone
                            status:
                              type: object
                              properties:
                                code:
                                  type: string
                                  description: code
                              description: status
                            spanMultipleDays:
                              type: boolean
                              description: spanMultipleDays
                          description: dates
                        classifications:
                          type: array
                          items:
                            type: object
                            properties:
                              primary:
                                type: boolean
                                description: primary
                              segment:
                                type: object
                                properties:
                                  id:
                                    type: string
                                    description: id
                                  name:
                                    type: string
                                    description: name
                                description: segment
                              genre:
                                type: object
                                properties:
                                  id:
                                    type: string
                                    description: id
                                  name:
                                    type: string
                                    description: name
                                description: genre
                              subGenre:
                                type: object
                                properties:
                                  id:
                                    type: string
                                    description: id
                                  name:
                                    type: string
                                    description: name
                                description: subGenre
                              type:
                                type: object
                                properties:
                                  id:
                                    type: string
                                    description: id
                                  name:
                                    type: string
                                    description: name
                                description: type
                              subType:
                                type: object
                                properties:
                                  id:
                                    type: string
                                    description: id
                                  name:
                                    type: string
                                    description: name
                                description: subType
                              family:
                                type: boolean
                                description: family
                          description: classifications
                        promoter:
                          type: object
                          properties:
                            id:
                              type: string
                              description: id
                            name:
                              type: string
                              description: name
                            description:
                              type: string
                              description: description
                          description: promoter
                        promoters:
                          type: array
                          items:
                            type: object
                            properties:
                              id:
                                type: string
                                description: id
                              name:
                                type: string
                                description: name
                              description:
                                type: string
                                description: description
                          description: promoters
                        info:
                          type: string
                          description: info
                        pleaseNote:
                          type: string
                          description: pleaseNote
                        seatmap:
                          type: object
                          properties:
                            staticUrl:
                              type: string
                              description: staticUrl
                            id:
                              type: string
                              description: id
                          description: seatmap
                        accessibility:
                          type: object
                          properties:
                            info:
                              type: string
                              description: info
                            ticketLimit:
                              type: integer
                              format: int32
                              description: ticketLimit
                            id:
                              type: string
                              description: id
                          description: accessibility
                        ticketLimit:
                          type: object
                          properties:
                            info:
                              type: string
                              description: info
                            id:
                              type: string
                              description: id
                          description: ticketLimit
                        ageRestrictions:
                          type: object
                          properties:
                            legalAgeEnforced:
                              type: boolean
                              description: legalAgeEnforced
                            id:
                              type: string
                              description: id
                          description: ageRestrictions
                        ticketing:
                          type: object
                          properties:
                            safeTix:
                              type: object
                              properties:
                                enabled:
                                  type: boolean
                                  description: enabled
                              description: safeTix
                            allInclusivePricing:
                              type: object
                              properties:
                                enabled:
                                  type: boolean
                                  description: enabled
                              description: allInclusivePricing
                            id:
                              type: string
                              description: id
                          description: ticketing
                        _links:
                          type: object
                          properties:
                            self:
                              type: object
                              properties:
                                href:
                                  type: string
                                  description: href
                              description: self
                            attractions:
                              type: array
                              items:
                                type: object
                                properties:
                                  href:
                                    type: string
                                    description: href
                              description: attractions
                            venues:
                              type: array
                              items:
                                type: object
                                properties:
                                  href:
                                    type: string
                                    description: href
                              description: venues
                          description: _links
                        _embedded:
                          type: object
                          properties:
                            venues:
                              type: array
                              items:
                                type: object
                                properties:
                                  name:
                                    type: string
                                    description: name
                                  type:
                                    type: string
                                    description: type
                                  id:
                                    type: string
                                    description: id
                                  test:
                                    type: boolean
                                    description: test
                                  url:
                                    type: string
                                    description: url
                                  locale:
                                    type: string
                                    description: locale
                                  images:
                                    type: array
                                    items:
                                      type: object
                                      properties:
                                        ratio:
                                          type: string
                                          description: ratio
                                        url:
                                          type: string
                                          description: url
                                        width:
                                          type: integer
                                          format: int32
                                          description: width
                                        height:
                                          type: integer
                                          format: int32
                                          description: height
                                        fallback:
                                          type: boolean
                                          description: fallback
                                    description: images
                                  postalCode:
                                    type: string
                                    description: postalCode
                                  timezone:
                                    type: string
                                    description: timezone
                                  city:
                                    type: object
                                    properties:
                                      name:
                                        type: string
                                        description: name
                                    description: city
                                  state:
                                    type: object
                                    properties:
                                      name:
                                        type: string
                                        description: name
                                      stateCode:
                                        type: string
                                        description: stateCode
                                    description: state
                                  country:
                                    type: object
                                    properties:
                                      name:
                                        type: string
                                        description: name
                                      countryCode:
                                        type: string
                                        description: countryCode
                                    description: country
                                  address:
                                    type: object
                                    properties:
                                      line1:
                                        type: string
                                        description: line1
                                    description: address
                                  location:
                                    type: object
                                    properties:
                                      longitude:
                                        type: string
                                        description: longitude
                                      latitude:
                                        type: string
                                        description: latitude
                                    description: location
                                  markets:
                                    type: array
                                    items:
                                      type: object
                                      properties:
                                        name:
                                          type: string
                                          description: name
                                        id:
                                          type: string
                                          description: id
                                    description: markets
                                  dmas:
                                    type: array
                                    items:
                                      type: object
                                      properties:
                                        id:
                                          type: integer
                                          format: int32
                                          description: id
                                    description: dmas
                                  boxOfficeInfo:
                                    type: object
                                    properties:
                                      openHoursDetail:
                                        type: string
                                        description: openHoursDetail
                                    description: boxOfficeInfo
                                  parkingDetail:
                                    type: string
                                    description: parkingDetail
                                  upcomingEvents:
                                    type: object
                                    properties:
                                      archtics:
                                        type: integer
                                        format: int32
                                        description: archtics
                                      tmr:
                                        type: integer
                                        format: int32
                                        description: tmr
                                      ticketmaster:
                                        type: integer
                                        format: int32
                                        description: ticketmaster
                                      _total:
                                        type: integer
                                        format: int32
                                        description: _total
                                      _filtered:
                                        type: integer
                                        format: int32
                                        description: _filtered
                                    description: upcomingEvents
                                  ada:
                                    type: object
                                    properties:
                                      adaPhones:
                                        type: string
                                        description: adaPhones
                                      adaCustomCopy:
                                        type: string
                                        description: adaCustomCopy
                                      adaHours:
                                        type: string
                                        description: adaHours
                                    description: ada
                                  _links:
                                    type: object
                                    properties:
                                      self:
                                        type: object
                                        properties:
                                          href:
                                            type: string
                                            description: href
                                        description: self
                                    description: _links
                              description: venues
                            attractions:
                              type: array
                              items:
                                type: object
                                properties:
                                  name:
                                    type: string
                                    description: name
                                  type:
                                    type: string
                                    description: type
                                  id:
                                    type: string
                                    description: id
                                  test:
                                    type: boolean
                                    description: test
                                  url:
                                    type: string
                                    description: url
                                  locale:
                                    type: string
                                    description: locale
                                  externalLinks:
                                    type: object
                                    properties:
                                      twitter:
                                        type: array
                                        items:
                                          type: object
                                          properties:
                                            url:
                                              type: string
                                              description: url
                                        description: twitter
                                      facebook:
                                        type: array
                                        items:
                                          type: object
                                          properties:
                                            url:
                                              type: string
                                              description: url
                                        description: facebook
                                      wiki:
                                        type: array
                                        items:
                                          type: object
                                          properties:
                                            url:
                                              type: string
                                              description: url
                                        description: wiki
                                      instagram:
                                        type: array
                                        items:
                                          type: object
                                          properties:
                                            url:
                                              type: string
                                              description: url
                                        description: instagram
                                      homepage:
                                        type: array
                                        items:
                                          type: object
                                          properties:
                                            url:
                                              type: string
                                              description: url
                                        description: homepage
                                    description: externalLinks
                                  images:
                                    type: array
                                    items:
                                      type: object
                                      properties:
                                        ratio:
                                          type: string
                                          description: ratio
                                        url:
                                          type: string
                                          description: url
                                        width:
                                          type: integer
                                          format: int32
                                          description: width
                                        height:
                                          type: integer
                                          format: int32
                                          description: height
                                        fallback:
                                          type: boolean
                                          description: fallback
                                        attribution:
                                          type: string
                                          description: attribution
                                    description: images
                                  classifications:
                                    type: array
                                    items:
                                      type: object
                                      properties:
                                        primary:
                                          type: boolean
                                          description: primary
                                        segment:
                                          type: object
                                          properties:
                                            id:
                                              type: string
                                              description: id
                                            name:
                                              type: string
                                              description: name
                                          description: segment
                                        genre:
                                          type: object
                                          properties:
                                            id:
                                              type: string
                                              description: id
                                            name:
                                              type: string
                                              description: name
                                          description: genre
                                        subGenre:
                                          type: object
                                          properties:
                                            id:
                                              type: string
                                              description: id
                                            name:
                                              type: string
                                              description: name
                                          description: subGenre
                                        type:
                                          type: object
                                          properties:
                                            id:
                                              type: string
                                              description: id
                                            name:
                                              type: string
                                              description: name
                                          description: type
                                        subType:
                                          type: object
                                          properties:
                                            id:
                                              type: string
                                              description: id
                                            name:
                                              type: string
                                              description: name
                                          description: subType
                                        family:
                                          type: boolean
                                          description: family
                                    description: classifications
                                  upcomingEvents:
                                    type: object
                                    properties:
                                      tmr:
                                        type: integer
                                        format: int32
                                        description: tmr
                                      ticketmaster:
                                        type: integer
                                        format: int32
                                        description: ticketmaster
                                      _total:
                                        type: integer
                                        format: int32
                                        description: _total
                                      _filtered:
                                        type: integer
                                        format: int32
                                        description: _filtered
                                    description: upcomingEvents
                                  _links:
                                    type: object
                                    properties:
                                      self:
                                        type: object
                                        properties:
                                          href:
                                            type: string
                                            description: href
                                        description: self
                                    description: _links
                                  aliases:
                                    type: array
                                    items:
                                      type: string
                                    description: aliases
                              description: attractions
                          description: _embedded
                    description: events
                description: _embedded
              _links:
                type: object
                properties:
                  first:
                    type: object
                    properties:
                      href:
                        type: string
                        description: href
                    description: first
                  self:
                    type: object
                    properties:
                      href:
                        type: string
                        description: href
                    description: self
                  next:
                    type: object
                    properties:
                      href:
                        type: string
                        description: href
                    description: next
                  last:
                    type: object
                    properties:
                      href:
                        type: string
                        description: href
                    description: last
                description: _links
              page:
                type: object
                properties:
                  size:
                    type: integer
                    format: int32
                    description: size
                  totalElements:
                    type: integer
                    format: int32
                    description: totalElements
                  totalPages:
                    type: integer
                    format: int32
                    description: totalPages
                  number:
                    type: integer
                    format: int32
                    description: number
                description: page
      summary: Get Events
      description: Retrieve events from Ticketmaster
      operationId: GetEvents
      x-ms-visibility: important
      parameters:
        - name: keyword
          in: query
          required: false
          type: string
        - name: StartDateTime
          in: query
          required: false
          type: string
        - name: city
          in: query
          required: false
          type: string
  /discovery/v2/events/{EventId}:
    get:
      responses:
        default:
          description: default
          schema:
            type: object
            properties:
              name:
                type: string
                description: name
              type:
                type: string
                description: type
              id:
                type: string
                description: id
              test:
                type: boolean
                description: test
              url:
                type: string
                description: url
              locale:
                type: string
                description: locale
              images:
                type: array
                items:
                  type: object
                  properties:
                    ratio:
                      type: string
                      description: ratio
                    url:
                      type: string
                      description: url
                    width:
                      type: integer
                      format: int32
                      description: width
                    height:
                      type: integer
                      format: int32
                      description: height
                    fallback:
                      type: boolean
                      description: fallback
                    attribution:
                      type: string
                      description: attribution
                description: images
              sales:
                type: object
                properties:
                  public:
                    type: object
                    properties:
                      startDateTime:
                        type: string
                        description: startDateTime
                      startTBD:
                        type: boolean
                        description: startTBD
                      startTBA:
                        type: boolean
                        description: startTBA
                      endDateTime:
                        type: string
                        description: endDateTime
                    description: public
                  presales:
                    type: array
                    items:
                      type: object
                      properties:
                        startDateTime:
                          type: string
                          description: startDateTime
                        endDateTime:
                          type: string
                          description: endDateTime
                        name:
                          type: string
                          description: name
                    description: presales
                description: sales
              dates:
                type: object
                properties:
                  start:
                    type: object
                    properties:
                      localDate:
                        type: string
                        description: localDate
                      localTime:
                        type: string
                        description: localTime
                      dateTime:
                        type: string
                        description: dateTime
                      dateTBD:
                        type: boolean
                        description: dateTBD
                      dateTBA:
                        type: boolean
                        description: dateTBA
                      timeTBA:
                        type: boolean
                        description: timeTBA
                      noSpecificTime:
                        type: boolean
                        description: noSpecificTime
                    description: start
                  timezone:
                    type: string
                    description: timezone
                  status:
                    type: object
                    properties:
                      code:
                        type: string
                        description: code
                    description: status
                  spanMultipleDays:
                    type: boolean
                    description: spanMultipleDays
                description: dates
              classifications:
                type: array
                items:
                  type: object
                  properties:
                    primary:
                      type: boolean
                      description: primary
                    segment:
                      type: object
                      properties:
                        id:
                          type: string
                          description: id
                        name:
                          type: string
                          description: name
                      description: segment
                    genre:
                      type: object
                      properties:
                        id:
                          type: string
                          description: id
                        name:
                          type: string
                          description: name
                      description: genre
                    subGenre:
                      type: object
                      properties:
                        id:
                          type: string
                          description: id
                        name:
                          type: string
                          description: name
                      description: subGenre
                    type:
                      type: object
                      properties:
                        id:
                          type: string
                          description: id
                        name:
                          type: string
                          description: name
                      description: type
                    subType:
                      type: object
                      properties:
                        id:
                          type: string
                          description: id
                        name:
                          type: string
                          description: name
                      description: subType
                    family:
                      type: boolean
                      description: family
                description: classifications
              promoter:
                type: object
                properties:
                  id:
                    type: string
                    description: id
                  name:
                    type: string
                    description: name
                  description:
                    type: string
                    description: description
                description: promoter
              promoters:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: string
                      description: id
                    name:
                      type: string
                      description: name
                    description:
                      type: string
                      description: description
                description: promoters
              info:
                type: string
                description: info
              pleaseNote:
                type: string
                description: pleaseNote
              seatmap:
                type: object
                properties:
                  staticUrl:
                    type: string
                    description: staticUrl
                  id:
                    type: string
                    description: id
                description: seatmap
              accessibility:
                type: object
                properties:
                  info:
                    type: string
                    description: info
                  ticketLimit:
                    type: integer
                    format: int32
                    description: ticketLimit
                  id:
                    type: string
                    description: id
                description: accessibility
              ticketLimit:
                type: object
                properties:
                  info:
                    type: string
                    description: info
                  id:
                    type: string
                    description: id
                description: ticketLimit
              ageRestrictions:
                type: object
                properties:
                  legalAgeEnforced:
                    type: boolean
                    description: legalAgeEnforced
                  id:
                    type: string
                    description: id
                description: ageRestrictions
              ticketing:
                type: object
                properties:
                  safeTix:
                    type: object
                    properties:
                      enabled:
                        type: boolean
                        description: enabled
                    description: safeTix
                  allInclusivePricing:
                    type: object
                    properties:
                      enabled:
                        type: boolean
                        description: enabled
                    description: allInclusivePricing
                  id:
                    type: string
                    description: id
                description: ticketing
              _links:
                type: object
                properties:
                  self:
                    type: object
                    properties:
                      href:
                        type: string
                        description: href
                    description: self
                  attractions:
                    type: array
                    items:
                      type: object
                      properties:
                        href:
                          type: string
                          description: href
                    description: attractions
                  venues:
                    type: array
                    items:
                      type: object
                      properties:
                        href:
                          type: string
                          description: href
                    description: venues
                description: _links
              _embedded:
                type: object
                properties:
                  venues:
                    type: array
                    items:
                      type: object
                      properties:
                        name:
                          type: string
                          description: name
                        type:
                          type: string
                          description: type
                        id:
                          type: string
                          description: id
                        test:
                          type: boolean
                          description: test
                        url:
                          type: string
                          description: url
                        locale:
                          type: string
                          description: locale
                        images:
                          type: array
                          items:
                            type: object
                            properties:
                              ratio:
                                type: string
                                description: ratio
                              url:
                                type: string
                                description: url
                              width:
                                type: integer
                                format: int32
                                description: width
                              height:
                                type: integer
                                format: int32
                                description: height
                              fallback:
                                type: boolean
                                description: fallback
                          description: images
                        postalCode:
                          type: string
                          description: postalCode
                        timezone:
                          type: string
                          description: timezone
                        city:
                          type: object
                          properties:
                            name:
                              type: string
                              description: name
                          description: city
                        state:
                          type: object
                          properties:
                            name:
                              type: string
                              description: name
                            stateCode:
                              type: string
                              description: stateCode
                          description: state
                        country:
                          type: object
                          properties:
                            name:
                              type: string
                              description: name
                            countryCode:
                              type: string
                              description: countryCode
                          description: country
                        address:
                          type: object
                          properties:
                            line1:
                              type: string
                              description: line1
                          description: address
                        location:
                          type: object
                          properties:
                            longitude:
                              type: string
                              description: longitude
                            latitude:
                              type: string
                              description: latitude
                          description: location
                        markets:
                          type: array
                          items:
                            type: object
                            properties:
                              name:
                                type: string
                                description: name
                              id:
                                type: string
                                description: id
                          description: markets
                        dmas:
                          type: array
                          items:
                            type: object
                            properties:
                              id:
                                type: integer
                                format: int32
                                description: id
                          description: dmas
                        boxOfficeInfo:
                          type: object
                          properties:
                            openHoursDetail:
                              type: string
                              description: openHoursDetail
                          description: boxOfficeInfo
                        parkingDetail:
                          type: string
                          description: parkingDetail
                        upcomingEvents:
                          type: object
                          properties:
                            archtics:
                              type: integer
                              format: int32
                              description: archtics
                            tmr:
                              type: integer
                              format: int32
                              description: tmr
                            ticketmaster:
                              type: integer
                              format: int32
                              description: ticketmaster
                            _total:
                              type: integer
                              format: int32
                              description: _total
                            _filtered:
                              type: integer
                              format: int32
                              description: _filtered
                          description: upcomingEvents
                        ada:
                          type: object
                          properties:
                            adaPhones:
                              type: string
                              description: adaPhones
                            adaCustomCopy:
                              type: string
                              description: adaCustomCopy
                            adaHours:
                              type: string
                              description: adaHours
                          description: ada
                        _links:
                          type: object
                          properties:
                            self:
                              type: object
                              properties:
                                href:
                                  type: string
                                  description: href
                              description: self
                          description: _links
                    description: venues
                  attractions:
                    type: array
                    items:
                      type: object
                      properties:
                        name:
                          type: string
                          description: name
                        type:
                          type: string
                          description: type
                        id:
                          type: string
                          description: id
                        test:
                          type: boolean
                          description: test
                        url:
                          type: string
                          description: url
                        locale:
                          type: string
                          description: locale
                        externalLinks:
                          type: object
                          properties:
                            twitter:
                              type: array
                              items:
                                type: object
                                properties:
                                  url:
                                    type: string
                                    description: url
                              description: twitter
                            facebook:
                              type: array
                              items:
                                type: object
                                properties:
                                  url:
                                    type: string
                                    description: url
                              description: facebook
                            wiki:
                              type: array
                              items:
                                type: object
                                properties:
                                  url:
                                    type: string
                                    description: url
                              description: wiki
                            instagram:
                              type: array
                              items:
                                type: object
                                properties:
                                  url:
                                    type: string
                                    description: url
                              description: instagram
                            homepage:
                              type: array
                              items:
                                type: object
                                properties:
                                  url:
                                    type: string
                                    description: url
                              description: homepage
                          description: externalLinks
                        images:
                          type: array
                          items:
                            type: object
                            properties:
                              ratio:
                                type: string
                                description: ratio
                              url:
                                type: string
                                description: url
                              width:
                                type: integer
                                format: int32
                                description: width
                              height:
                                type: integer
                                format: int32
                                description: height
                              fallback:
                                type: boolean
                                description: fallback
                              attribution:
                                type: string
                                description: attribution
                          description: images
                        classifications:
                          type: array
                          items:
                            type: object
                            properties:
                              primary:
                                type: boolean
                                description: primary
                              segment:
                                type: object
                                properties:
                                  id:
                                    type: string
                                    description: id
                                  name:
                                    type: string
                                    description: name
                                description: segment
                              genre:
                                type: object
                                properties:
                                  id:
                                    type: string
                                    description: id
                                  name:
                                    type: string
                                    description: name
                                description: genre
                              subGenre:
                                type: object
                                properties:
                                  id:
                                    type: string
                                    description: id
                                  name:
                                    type: string
                                    description: name
                                description: subGenre
                              type:
                                type: object
                                properties:
                                  id:
                                    type: string
                                    description: id
                                  name:
                                    type: string
                                    description: name
                                description: type
                              subType:
                                type: object
                                properties:
                                  id:
                                    type: string
                                    description: id
                                  name:
                                    type: string
                                    description: name
                                description: subType
                              family:
                                type: boolean
                                description: family
                          description: classifications
                        upcomingEvents:
                          type: object
                          properties:
                            tmr:
                              type: integer
                              format: int32
                              description: tmr
                            ticketmaster:
                              type: integer
                              format: int32
                              description: ticketmaster
                            _total:
                              type: integer
                              format: int32
                              description: _total
                            _filtered:
                              type: integer
                              format: int32
                              description: _filtered
                          description: upcomingEvents
                        _links:
                          type: object
                          properties:
                            self:
                              type: object
                              properties:
                                href:
                                  type: string
                                  description: href
                              description: self
                          description: _links
                        aliases:
                          type: array
                          items:
                            type: string
                          description: aliases
                    description: attractions
                description: _embedded
      summary: Get Event in detail
      description: GetEventDetail
      operationId: GetEventDetail
      x-ms-visibility: important
      parameters:
        - name: EventId
          in: path
          required: true
          type: string
          x-ms-visibility: important
definitions: {}
parameters: {}
responses: {}
securityDefinitions:
  api_key:
    type: apiKey
    in: query
    name: apikey
security:
  - api_key: []
tags: []

```

### Tool of Get Event in detail
```
kind: TaskDialog
modelDisplayName: Get Event in detail
modelDescription: GetEventDetail
outputs:
  - propertyName: _embedded.attractions

  - propertyName: _embedded.venues

  - propertyName: _links.attractions

  - propertyName: _links.self.href

  - propertyName: _links.venues

  - propertyName: accessibility.id

  - propertyName: accessibility.info

  - propertyName: accessibility.ticketLimit

  - propertyName: ageRestrictions.id

  - propertyName: ageRestrictions.legalAgeEnforced

  - propertyName: classifications

  - propertyName: dates.spanMultipleDays

  - propertyName: dates.start.dateTBA

  - propertyName: dates.start.dateTBD

  - propertyName: dates.start.dateTime

  - propertyName: dates.start.localDate

  - propertyName: dates.start.localTime

  - propertyName: dates.start.noSpecificTime

  - propertyName: dates.start.timeTBA

  - propertyName: dates.status.code

  - propertyName: dates.timezone

  - propertyName: id

  - propertyName: images

  - propertyName: info

  - propertyName: locale

  - propertyName: name

  - propertyName: pleaseNote

  - propertyName: promoter.description

  - propertyName: promoter.id

  - propertyName: promoter.name

  - propertyName: promoters

  - propertyName: sales.presales

  - propertyName: sales.public.endDateTime

  - propertyName: sales.public.startDateTime

  - propertyName: sales.public.startTBA

  - propertyName: sales.public.startTBD

  - propertyName: seatmap.id

  - propertyName: seatmap.staticUrl

  - propertyName: test

  - propertyName: ticketing.allInclusivePricing.enabled

  - propertyName: ticketing.id

  - propertyName: ticketing.safeTix.enabled

  - propertyName: ticketLimit.id

  - propertyName: ticketLimit.info

  - propertyName: type

  - propertyName: url

action:
  kind: InvokeConnectorTaskAction
  connectionReference: cr202_ticketMaster.shared_ticketmaster-5f9f1743201ee220d8-5f8162bc61f529b2c6.dbaebfa663a64e3096b4eb424248ef82
  connectionProperties:
    mode: Invoker

  operationId: GetEventDetail

outputMode: All
```


```
kind: TaskDialog
inputs:
  - kind: AutomaticTaskInput
    propertyName: city
    name: city
    description: |-
      - 이벤트 또는 공연이 열리는 도시 이름을 인식합니다. 모든 도시의 이름은 영어로 변경되어야 합니다.
      예: 서울 -> Seoul, 뉴욕 -> New York

      - 그렇지 않으면 공백으로 유지합니다
    shouldPromptUser: false

  - kind: AutomaticTaskInput
    propertyName: keyword
    name: keyword
    description: "공연 및 이벤트, 가수 이름 등의 키워드입니다. "
    shouldPromptUser: true

  - kind: AutomaticTaskInput
    propertyName: StartDateTime
    name: StartDateTime
    description: |-
      - 공연 또는 이벤트가 열리는 시작 날짜입니다. 입력된 날짜가 없다면 공백으로 유지합니다.
      - 입력된 날짜가 있다면, 반드시 날짜의 공통 형식인 ISO8601을 따라서 포멧을 변경합니다.
      예 1) ISO8601 형식에서 날짜는 yyyy-MM-ddthh:mm:ssz 으로 표현합니다.
      예 2) 고객이 날짜 형식을 '25-6-15'를 입력했다면? '2025-06-15T00:00:00Z' 으로 표현됩니다.

modelDisplayName: Get Events
modelDescription: "Ticketmaster에서 각종 공연 및 이벤트 정보를 조회합니다. 그리고 유효한 이벤트 & 공연을 bullet mark 형태로 표현합니다. "
outputs:
  - propertyName: _embedded.events

  - propertyName: _links.first.href

  - propertyName: _links.last.href

  - propertyName: _links.next.href

  - propertyName: _links.self.href

  - propertyName: page.number

  - propertyName: page.size

  - propertyName: page.totalElements

  - propertyName: page.totalPages

action:
  kind: InvokeConnectorTaskAction
  connectionReference: cr202_ticketMaster.shared_ticketmaster-5f9f1743201ee220d8-5f8162bc61f529b2c6.33a3f201345d47928c643e654733f1d7
  connectionProperties:
    mode: Invoker

  operationId: GetEvents

outputMode: All
```
