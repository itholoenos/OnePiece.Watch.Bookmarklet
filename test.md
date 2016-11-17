             
```razor
@model SubmitFormMvcEFcf.Models.DataUser  
@{
   ViewBag.Title = "Home Page";  
} 
          
<div class="row">
 <div class="col-md-12 col-sm-12 col-lg-12 col-xs-12">
         @using (Html.BeginForm("Index", "Home", FormMethod.Post, new { role = "form" }))
        {
            @Html.AntiForgeryToken()
            <h4>@ViewBag.Message</h4>
            <hr />
            @Html.ValidationSummary("", new { @class = "text-danger" })
           
            <div class="form-group">
                @Html.LabelFor(m => m.FirstName, new { @class = "control-label" });
                @Html.TextBoxFor(m => m.FirstName, new { @class = "form-control" })
            </div>
            <div class="form-group">
                @Html.LabelFor(m => m.LastName, new { @class = "control-label" })
                @Html.TextBoxFor(m => m.LastName, new { @class = "form-control" })
            </div>
            <div class="form-group">
                @Html.LabelFor(m => m.Telephone, new { @class = "control-label" })
                @Html.TextBoxFor(m => m.Telephone, new { @class = "form-control" })
            </div>
            <div class="form-group">
                @Html.LabelFor(m => m.Email, new { @class = "control-label" })
                @Html.TextBoxFor(m => m.Email, new { @class = "form-control" })
            </div>
            <div class="form-group">
                @Html.LabelFor(m => m.Gender, new { @class = "control-label" })
            <span>Male:</span>
                @Html.RadioButtonFor(m => m.Gender, "male")
            <span>Female:</span>
                @Html.RadioButtonFor(m => m.Gender, "female")
            </div>
            <div class="form-group">
            <input type="submit" class="btn btn-info" value="Submit" />
                  </div>
            
 </div>
</div>
        }
        ```
