# use the function that in another function body, has two method
## method 1
    function body()
    {
      function chlid(x, y)
      {
        console.log('hello world', x * y)
      }
      return chlid
    }
    body = body() / chlid = body()
    body(2, 3) / chlid(2, 3)
    // output: hello world 6
## method 2
      function body()
      {
        function chlid(x, y)
        {
          console.log('hello world', x * y)
        }
        chlid(2, 3)
      }
      body(2, 3)
      // output: hello world 6
