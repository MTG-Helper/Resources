  public async void POSTreq()
        {  
            Uri requestUri = new Uri("http://localhost:9000/stats");  
            dynamic dynamicJson = new ExpandoObject();  
            dynamicJson.quantityDownloadedCardsImages = "20";  
            dynamicJson.quantitySearchedCards = "40";  
            string json = "";  
            json = Newtonsoft.Json.JsonConvert.SerializeObject(dynamicJson);  
            var objClint = new System.Net.Http.HttpClient();  
            System.Net.Http.HttpResponseMessage respon = await objClint.PostAsync(requestUri, new StringContent(json, System.Text.Encoding.UTF8, "application/json"));  
            string responJsonText = await respon.Content.ReadAsStringAsync();  
        }
