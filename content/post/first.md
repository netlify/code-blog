+++
date = "2016-06-08T11:12:17-07:00"
draft = true
title = "first"
author = "Brian"

+++

This is a test post


Lo-fi humblebrag bitters, roof party small batch chambray pop-up butcher sriracha sartorial vegan messenger bag austin. Keffiyeh hoodie aesthetic, beard ennui single-origin coffee truffaut PBR&B flannel food truck offal messenger bag tattooed narwhal pickled. Farm-to-table craft beer messenger bag butcher godard green juice. Drinking vinegar listicle church-key tacos art party single-origin coffee. Schlitz seitan vegan, offal meditation cronut paleo bespoke keytar pabst. Banjo quinoa freegan, wayfarers ugh kitsch bespoke slow-carb brooklyn. Synth umami williamsburg migas cornhole pour-over irony, whatever vice photo booth chambray 3 wolf moon PBR&B swag.

```go
func main() {
As before we’ll count how many operations we perform.
    var ops int64 = 0
The reads and writes channels will be used by other goroutines to issue read and write requests, respectively.
    reads := make(chan *readOp)
    writes := make(chan *writeOp)
Here is the goroutine that owns the state, which is a map as in the previous example but now private to the stateful goroutine. This goroutine repeatedly selects on the reads and writes channels, responding to requests as they arrive. A response is executed by first performing the requested operation and then sending a value on the response channel resp to indicate success (and the desired value in the case of reads).
    go func() {
        var state = make(map[int]int)
        for {
            select {
            case read := <-reads:
                read.resp <- state[read.key]
            case write := <-writes:
                state[write.key] = write.val
                write.resp <- true
            }
        }
    }()
}
```

Portland keffiyeh microdosing, retro chillwave actually flannel. Fingerstache yr asymmetrical irony, williamsburg normcore fanny pack chartreuse man braid waistcoat organic authentic. Readymade migas mustache pug, drinking vinegar direct trade sustainable farm-to-table pour-over. Fingerstache austin microdosing leggings master cleanse franzen. Mustache meditation vinyl typewriter lumbersexual gastropub hashtag, authentic cornhole kitsch street art occupy irony chicharrones tumblr. Paleo DIY artisan, cliche kitsch shoreditch green juice pour-over helvetica forage. Intelligentsia kinfolk chartreuse, tote bag XOXO venmo cred.


