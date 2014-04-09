public Random random = new Random();

protected void Page_Load(object sender, EventArgs e)
{
    // # columns, # rows, useNumeric (T/F), rowLength, minNumber, maxNumber
    LoadGridView(4, 12, true, 14, 500, 1500);
}

public void LoadGridView(int columnCount, int rowCount, bool useNumeric, int rowLength, int minNumber, int maxNumber)
{
    DataTable dt = new DataTable();
    dt.Columns.Add(new DataColumn(" ", typeof(string)));

    for (int c = 0; c < columnCount; c++)
    {
        string columnName = RandomString(rowLength, false);
        if(useNumeric==true)
        {
            dt.Columns.Add(new DataColumn(columnName, typeof(Int32)));
        }
        else

        {
            dt.Columns.Add(new DataColumn(columnName, typeof(string)));
        }
    }           

    for (int j = 1; j <= rowCount; j++)
    {
        DataRow dr = dt.NewRow();
        dr[0] = RandomString(4, false);
        for (int k = 1; k <= columnCount; k++)
        {
            if (useNumeric == true)
            {
                dr[k] = RandomNumber(minNumber, maxNumber);
            }
            else

            {
                dr[k] = RandomString(rowLength, true);
            }
        }
        dt.Rows.Add(dr);
    }

    gvExample.DataSource = dt;
    gvExample.DataBind();
}

private int RandomNumber(int min, int max)
{
    return random.Next(min, max);
}

private string RandomString(int size, bool lowerCase)
{
    StringBuilder builder = new StringBuilder();
    char ch;
    for (int i = 0; i < size; i++)
    {
        ch = Convert.ToChar(Convert.ToInt32(Math.Floor(26 * random.NextDouble() + 65)));
        builder.Append(ch);
    }
    if (lowerCase)
        return builder.ToString().ToLower();
    return builder.ToString();
}
