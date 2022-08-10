local random = Random.new()
local letters = {'1','2','3','4','5','6','7','8','9','0','a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'}
function getRandomLetter()
    return letters[random:NextInteger(1,#letters)]
end


function getRandomString(length, includeCapitals)
    local length = 10
    local str = ''
    for i=1,length do
        local randomLetter = getRandomLetter()
        if includeCapitals and random:NextNumber() > .5 then
            randomLetter = string.upper(randomLetter)
        end
        str = str .. randomLetter
    end
    return str
end


for i=1,times do
   local code = "pet-"..getRandomString(true)
   print(code.." has been redeemed")
   -- This was generated from engospy RemoteSpy tool.
workspace.__THINGS.__REMOTES["redeem merch code"]:InvokeServer({
    [1] = code,
})
   wait(.1)
   local randomc = math.random(1,40)
end
